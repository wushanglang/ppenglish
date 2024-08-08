<template>
  <div class="editor" spellcheck="false">
    <editor-content :editor="editor" />
  </div>
</template>

<script>
import { Color } from "@tiptap/extension-color";
import ListItem from "@tiptap/extension-list-item";
import TextStyle from "@tiptap/extension-text-style";
import StarterKit from "@tiptap/starter-kit";
import { Editor, EditorContent } from "@tiptap/vue-2";
import { openDatabase, saveContent, getContent } from "../util/dbHelper";

export default {
  components: {
    EditorContent,
  },

  data() {
    return {
      editor: null,
      content: "",
      dbName: "ppdb",
      storeName: "pptb",
    };
  },

  async mounted() {
    const db = await openDatabase(this.dbName, this.storeName);
    const key = this.$route.fullPath;
    const storedContent = await getContent(db, this.storeName, key);

    this.editor = new Editor({
      extensions: [
        Color.configure({ types: [TextStyle.name, ListItem.name] }),
        TextStyle.configure({ types: [ListItem.name] }),
        StarterKit,
      ],
      content: storedContent || "",
    });

    this.editor.on("update", async ({ editor }) => {
      this.content = editor.getHTML();
      await saveContent(db, this.storeName, this.content, key);
    });
  },

  beforeUnmount() {
    this.editor.destroy();
  },
};
</script>

<style scoped>
.editor {
  text-align: left;
  position: fixed;
  right: 0;
  top: 48%;
  color: #222;
  background-color: #eeeeee;
  border-radius: 8px;
}
</style>

<template>
    <mavon-editor style="height: 100%" v-model="code" :short-cut="false" :css-bgc="cssBgc.dark" :codeStyle="codeStyle" :xssOptions="xssOptions"></mavon-editor>
</template>
<script>
import styles from '../lib/core/hljs/lang.hljs.css.js'

const code = `java
/**
 * @author John Smith <john.smith@example.com>
*/
package l2f.gameserver.model;

public abstract strictfp class L2Char extends L2Object {
  public static final Short ERROR = 0x0001;

  public void moveTo(int x, int y, int z) {
    _ai = null;
    log("Should not be called");
    if (1 > 5) { // wtf!?
      return;
    }
  }
}`;

module.exports = {
    name: 'editor',
    data: function () {
        return {
            codeStyle: "github",
            styles,
            code: '<span style="color:red;font-size:36px;">A</span> \n```' + code + '\n```',
            xssOptions:{
                whiteList: {
                    span: ['style']
                }
            },
            cssBgc: {
                dark: {
                    toolbarBgc: 'aquamarine',
                    toolbarButtonHoverBgc: 'green',
                },
                light: {
                }
            }
        };
    }
}
</script>
<style>
body {
    background-color: #181c27;
}
.container {
    margin: auto;
    width: 80%;
}
#editor {
    height: 580px;
}
.switch-code-style {
    margin-top: 10px;
    font-size: 16px;
}




#root.dark {
    color-scheme: dark;
    --body-bg-color: #181c27;
    --board-bg-color: #252d38;
    --text-color: #c4c6c9;
    --sec-text-color: #a7a9ad;
    --post-text-color: #c4c6c9;
    --post-heading-color: #c4c6c9;
    --post-link-color: #1589e9;
    --nine-color: #00A2EA;
    --link-hover-color: #30a9de;
    --link-hover-bg-color: #364151;
    --line-color: #435266;
    --navbar-bg-color: #1f3144;
    --navbar-text-color: #d0d0d0;
    --subtitle-color: #d0d0d0;
    --scrollbar-color: #687582;
    --scrollbar-hover-color: #9da8b3;
    --button-bg-color: transparent;
    --button-hover-bg-color: #46647e;
    --highlight-bg-color: #444;
    --inlinecode-bg-color: rgba(99,110,123,0.4);
    --jiude-blue: #00a2ea;
}
#root.light {
    color-scheme: light;
    --color-mode: "light";
    --body-bg-color: #eee;
    --board-bg-color: #fff;
    --text-color: #3c4858;
    --sec-text-color: #718096;
    --post-text-color: #2c3e50;
    --post-heading-color: #1a202c;
    --post-link-color: #0366d6;
    --nine-color: #00b3ff;
    --link-hover-color: #30a9de;
    --link-hover-bg-color: #f8f9fa;
    --line-color: #eaecef;
    --navbar-bg-color: #2f4154;
    --navbar-text-color: #fff;
    --subtitle-color: #fff;
    --scrollbar-color: #c4c6c9;
    --scrollbar-hover-color: #a6a6a6;
    --button-bg-color: transparent;
    --button-hover-bg-color: #f2f3f5;
    --highlight-bg-color: #f6f8fa;
    --inlinecode-bg-color: rgba(175,184,193,0.2);
    --jiude-blue: #00a2ea;
}
</style>

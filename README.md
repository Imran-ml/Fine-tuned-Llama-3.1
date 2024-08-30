<!DOCTYPE html>

<html lang="en">
<head><meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<title>llama3_1_mental_health</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<style type="text/css">
    pre { line-height: 125%; }
td.linenos .normal { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
span.linenos { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
td.linenos .special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
span.linenos.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
.highlight .hll { background-color: var(--jp-cell-editor-active-background) }
.highlight { background: var(--jp-cell-editor-background); color: var(--jp-mirror-editor-variable-color) }
.highlight .c { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment */
.highlight .err { color: var(--jp-mirror-editor-error-color) } /* Error */
.highlight .k { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword */
.highlight .o { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator */
.highlight .p { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation */
.highlight .ch { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Multiline */
.highlight .cp { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Preproc */
.highlight .cpf { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Single */
.highlight .cs { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Special */
.highlight .kc { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Pseudo */
.highlight .kr { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Type */
.highlight .m { color: var(--jp-mirror-editor-number-color) } /* Literal.Number */
.highlight .s { color: var(--jp-mirror-editor-string-color) } /* Literal.String */
.highlight .ow { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator.Word */
.highlight .pm { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation.Marker */
.highlight .w { color: var(--jp-mirror-editor-variable-color) } /* Text.Whitespace */
.highlight .mb { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Bin */
.highlight .mf { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Float */
.highlight .mh { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Hex */
.highlight .mi { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer */
.highlight .mo { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Oct */
.highlight .sa { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Affix */
.highlight .sb { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Backtick */
.highlight .sc { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Char */
.highlight .dl { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Delimiter */
.highlight .sd { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Doc */
.highlight .s2 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Double */
.highlight .se { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Escape */
.highlight .sh { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Heredoc */
.highlight .si { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Interpol */
.highlight .sx { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Other */
.highlight .sr { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Regex */
.highlight .s1 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Single */
.highlight .ss { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Symbol */
.highlight .il { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer.Long */
  </style>
<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
 * Mozilla scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */
[data-jp-theme-scrollbars='true'] {
  scrollbar-color: rgb(var(--jp-scrollbar-thumb-color))
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar. These selectors
 * will match lower in the tree, and so will override the above */
[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
}

/* tiny scrollbar */

.jp-scrollbar-tiny {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
  scrollbar-width: thin;
}

/* tiny scrollbar */

.jp-scrollbar-tiny::-webkit-scrollbar,
.jp-scrollbar-tiny::-webkit-scrollbar-corner {
  background-color: transparent;
  height: 4px;
  width: 4px;
}

.jp-scrollbar-tiny::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:horizontal {
  border-left: 0 solid transparent;
  border-right: 0 solid transparent;
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:vertical {
  border-top: 0 solid transparent;
  border-bottom: 0 solid transparent;
}

/*
 * Lumino
 */

.lm-ScrollBar[data-orientation='horizontal'] {
  min-height: 16px;
  max-height: 16px;
  min-width: 45px;
  border-top: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] {
  min-width: 16px;
  max-width: 16px;
  min-height: 45px;
  border-left: 1px solid #a0a0a0;
}

.lm-ScrollBar-button {
  background-color: #f0f0f0;
  background-position: center center;
  min-height: 15px;
  max-height: 15px;
  min-width: 15px;
  max-width: 15px;
}

.lm-ScrollBar-button:hover {
  background-color: #dadada;
}

.lm-ScrollBar-button.lm-mod-active {
  background-color: #cdcdcd;
}

.lm-ScrollBar-track {
  background: #f0f0f0;
}

.lm-ScrollBar-thumb {
  background: #cdcdcd;
}

.lm-ScrollBar-thumb:hover {
  background: #bababa;
}

.lm-ScrollBar-thumb.lm-mod-active {
  background: #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal'] .lm-ScrollBar-thumb {
  height: 100%;
  min-width: 15px;
  border-left: 1px solid #a0a0a0;
  border-right: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] .lm-ScrollBar-thumb {
  width: 100%;
  min-height: 15px;
  border-top: 1px solid #a0a0a0;
  border-bottom: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-left);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-right);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-up);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-down);
  background-size: 17px;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-Widget {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
}

.lm-Widget.lm-mod-hidden {
  display: none !important;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.lm-AccordionPanel[data-orientation='horizontal'] > .lm-AccordionPanel-title {
  /* Title is rotated for horizontal accordion panel using CSS */
  display: block;
  transform-origin: top left;
  transform: rotate(-90deg) translate(-100%);
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  display: flex;
  flex-direction: column;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-CommandPalette-search {
  flex: 0 0 auto;
}

.lm-CommandPalette-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  min-height: 0;
  overflow: auto;
  list-style-type: none;
}

.lm-CommandPalette-header {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.lm-CommandPalette-item {
  display: flex;
  flex-direction: row;
}

.lm-CommandPalette-itemIcon {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemContent {
  flex: 1 1 auto;
  overflow: hidden;
}

.lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemLabel {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.lm-close-icon {
  border: 1px solid transparent;
  background-color: transparent;
  position: absolute;
  z-index: 1;
  right: 3%;
  top: 0;
  bottom: 0;
  margin: auto;
  padding: 7px 0;
  display: none;
  vertical-align: middle;
  outline: 0;
  cursor: pointer;
}
.lm-close-icon:after {
  content: 'X';
  display: block;
  width: 15px;
  height: 15px;
  text-align: center;
  color: #000;
  font-weight: normal;
  font-size: 12px;
  cursor: pointer;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-DockPanel {
  z-index: 0;
}

.lm-DockPanel-widget {
  z-index: 0;
}

.lm-DockPanel-tabBar {
  z-index: 1;
}

.lm-DockPanel-handle {
  z-index: 2;
}

.lm-DockPanel-handle.lm-mod-hidden {
  display: none !important;
}

.lm-DockPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}

.lm-DockPanel-handle[data-orientation='horizontal'] {
  cursor: ew-resize;
}

.lm-DockPanel-handle[data-orientation='vertical'] {
  cursor: ns-resize;
}

.lm-DockPanel-handle[data-orientation='horizontal']:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}

.lm-DockPanel-handle[data-orientation='vertical']:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

.lm-DockPanel-overlay {
  z-index: 3;
  box-sizing: border-box;
  pointer-events: none;
}

.lm-DockPanel-overlay.lm-mod-hidden {
  display: none !important;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-Menu {
  z-index: 10000;
  position: absolute;
  white-space: nowrap;
  overflow-x: hidden;
  overflow-y: auto;
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-Menu-content {
  margin: 0;
  padding: 0;
  display: table;
  list-style-type: none;
}

.lm-Menu-item {
  display: table-row;
}

.lm-Menu-item.lm-mod-hidden,
.lm-Menu-item.lm-mod-collapsed {
  display: none !important;
}

.lm-Menu-itemIcon,
.lm-Menu-itemSubmenuIcon {
  display: table-cell;
  text-align: center;
}

.lm-Menu-itemLabel {
  display: table-cell;
  text-align: left;
}

.lm-Menu-itemShortcut {
  display: table-cell;
  text-align: right;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-MenuBar {
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-MenuBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
  list-style-type: none;
}

.lm-MenuBar-item {
  box-sizing: border-box;
}

.lm-MenuBar-itemIcon,
.lm-MenuBar-itemLabel {
  display: inline-block;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-ScrollBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-ScrollBar[data-orientation='horizontal'] {
  flex-direction: row;
}

.lm-ScrollBar[data-orientation='vertical'] {
  flex-direction: column;
}

.lm-ScrollBar-button {
  box-sizing: border-box;
  flex: 0 0 auto;
}

.lm-ScrollBar-track {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  flex: 1 1 auto;
}

.lm-ScrollBar-thumb {
  box-sizing: border-box;
  position: absolute;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-SplitPanel-child {
  z-index: 0;
}

.lm-SplitPanel-handle {
  z-index: 1;
}

.lm-SplitPanel-handle.lm-mod-hidden {
  display: none !important;
}

.lm-SplitPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}

.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle {
  cursor: ew-resize;
}

.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle {
  cursor: ns-resize;
}

.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}

.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-TabBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-TabBar[data-orientation='horizontal'] {
  flex-direction: row;
  align-items: flex-end;
}

.lm-TabBar[data-orientation='vertical'] {
  flex-direction: column;
  align-items: flex-end;
}

.lm-TabBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex: 1 1 auto;
  list-style-type: none;
}

.lm-TabBar[data-orientation='horizontal'] > .lm-TabBar-content {
  flex-direction: row;
}

.lm-TabBar[data-orientation='vertical'] > .lm-TabBar-content {
  flex-direction: column;
}

.lm-TabBar-tab {
  display: flex;
  flex-direction: row;
  box-sizing: border-box;
  overflow: hidden;
  touch-action: none; /* Disable native Drag/Drop */
}

.lm-TabBar-tabIcon,
.lm-TabBar-tabCloseIcon {
  flex: 0 0 auto;
}

.lm-TabBar-tabLabel {
  flex: 1 1 auto;
  overflow: hidden;
  white-space: nowrap;
}

.lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing: border-box;
}

.lm-TabBar-tab.lm-mod-hidden {
  display: none !important;
}

.lm-TabBar-addButton.lm-mod-hidden {
  display: none !important;
}

.lm-TabBar.lm-mod-dragging .lm-TabBar-tab {
  position: relative;
}

.lm-TabBar.lm-mod-dragging[data-orientation='horizontal'] .lm-TabBar-tab {
  left: 0;
  transition: left 150ms ease;
}

.lm-TabBar.lm-mod-dragging[data-orientation='vertical'] .lm-TabBar-tab {
  top: 0;
  transition: top 150ms ease;
}

.lm-TabBar.lm-mod-dragging .lm-TabBar-tab.lm-mod-dragging {
  transition: none;
}

.lm-TabBar-tabLabel .lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing: border-box;
  background: inherit;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-TabPanel-tabBar {
  z-index: 1;
}

.lm-TabPanel-stackedPanel {
  z-index: 0;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapse {
  display: flex;
  flex-direction: column;
  align-items: stretch;
}

.jp-Collapse-header {
  padding: 1px 12px;
  background-color: var(--jp-layout-color1);
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  align-items: center;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  text-transform: uppercase;
  user-select: none;
}

.jp-Collapser-icon {
  height: 16px;
}

.jp-Collapse-header-collapsed .jp-Collapser-icon {
  transform: rotate(-90deg);
  margin: auto 0;
}

.jp-Collapser-title {
  line-height: 25px;
}

.jp-Collapse-contents {
  padding: 0 12px;
  background-color: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensureUiComponents() in @jupyterlab/buildutils */

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

/* Icons urls */

:root {
  --jp-icon-add-above: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPGcgY2xpcC1wYXRoPSJ1cmwoI2NsaXAwXzEzN18xOTQ5MikiPgo8cGF0aCBjbGFzcz0ianAtaWNvbjMiIGQ9Ik00Ljc1IDQuOTMwNjZINi42MjVWNi44MDU2NkM2LjYyNSA3LjAxMTkxIDYuNzkzNzUgNy4xODA2NiA3IDcuMTgwNjZDNy4yMDYyNSA3LjE4MDY2IDcuMzc1IDcuMDExOTEgNy4zNzUgNi44MDU2NlY0LjkzMDY2SDkuMjVDOS40NTYyNSA0LjkzMDY2IDkuNjI1IDQuNzYxOTEgOS42MjUgNC41NTU2NkM5LjYyNSA0LjM0OTQxIDkuNDU2MjUgNC4xODA2NiA5LjI1IDQuMTgwNjZINy4zNzVWMi4zMDU2NkM3LjM3NSAyLjA5OTQxIDcuMjA2MjUgMS45MzA2NiA3IDEuOTMwNjZDNi43OTM3NSAxLjkzMDY2IDYuNjI1IDIuMDk5NDEgNi42MjUgMi4zMDU2NlY0LjE4MDY2SDQuNzVDNC41NDM3NSA0LjE4MDY2IDQuMzc1IDQuMzQ5NDEgNC4zNzUgNC41NTU2NkM0LjM3NSA0Ljc2MTkxIDQuNTQzNzUgNC45MzA2NiA0Ljc1IDQuOTMwNjZaIiBmaWxsPSIjNjE2MTYxIiBzdHJva2U9IiM2MTYxNjEiIHN0cm9rZS13aWR0aD0iMC43Ii8+CjwvZz4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiIGNsaXAtcnVsZT0iZXZlbm9kZCIgZD0iTTExLjUgOS41VjExLjVMMi41IDExLjVWOS41TDExLjUgOS41Wk0xMiA4QzEyLjU1MjMgOCAxMyA4LjQ0NzcyIDEzIDlWMTJDMTMgMTIuNTUyMyAxMi41NTIzIDEzIDEyIDEzTDIgMTNDMS40NDc3MiAxMyAxIDEyLjU1MjMgMSAxMlY5QzEgOC40NDc3MiAxLjQ0NzcxIDggMiA4TDEyIDhaIiBmaWxsPSIjNjE2MTYxIi8+CjxkZWZzPgo8Y2xpcFBhdGggaWQ9ImNsaXAwXzEzN18xOTQ5MiI+CjxyZWN0IGNsYXNzPSJqcC1pY29uMyIgd2lkdGg9IjYiIGhlaWdodD0iNiIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0ibWF0cml4KC0xIDAgMCAxIDEwIDEuNTU1NjYpIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==);
  --jp-icon-add-below: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPGcgY2xpcC1wYXRoPSJ1cmwoI2NsaXAwXzEzN18xOTQ5OCkiPgo8cGF0aCBjbGFzcz0ianAtaWNvbjMiIGQ9Ik05LjI1IDEwLjA2OTNMNy4zNzUgMTAuMDY5M0w3LjM3NSA4LjE5NDM0QzcuMzc1IDcuOTg4MDkgNy4yMDYyNSA3LjgxOTM0IDcgNy44MTkzNEM2Ljc5Mzc1IDcuODE5MzQgNi42MjUgNy45ODgwOSA2LjYyNSA4LjE5NDM0TDYuNjI1IDEwLjA2OTNMNC43NSAxMC4wNjkzQzQuNTQzNzUgMTAuMDY5MyA0LjM3NSAxMC4yMzgxIDQuMzc1IDEwLjQ0NDNDNC4zNzUgMTAuNjUwNiA0LjU0Mzc1IDEwLjgxOTMgNC43NSAxMC44MTkzTDYuNjI1IDEwLjgxOTNMNi42MjUgMTIuNjk0M0M2LjYyNSAxMi45MDA2IDYuNzkzNzUgMTMuMDY5MyA3IDEzLjA2OTNDNy4yMDYyNSAxMy4wNjkzIDcuMzc1IDEyLjkwMDYgNy4zNzUgMTIuNjk0M0w3LjM3NSAxMC44MTkzTDkuMjUgMTAuODE5M0M5LjQ1NjI1IDEwLjgxOTMgOS42MjUgMTAuNjUwNiA5LjYyNSAxMC40NDQzQzkuNjI1IDEwLjIzODEgOS40NTYyNSAxMC4wNjkzIDkuMjUgMTAuMDY5M1oiIGZpbGw9IiM2MTYxNjEiIHN0cm9rZT0iIzYxNjE2MSIgc3Ryb2tlLXdpZHRoPSIwLjciLz4KPC9nPgo8cGF0aCBjbGFzcz0ianAtaWNvbjMiIGZpbGwtcnVsZT0iZXZlbm9kZCIgY2xpcC1ydWxlPSJldmVub2RkIiBkPSJNMi41IDUuNUwyLjUgMy41TDExLjUgMy41TDExLjUgNS41TDIuNSA1LjVaTTIgN0MxLjQ0NzcyIDcgMSA2LjU1MjI4IDEgNkwxIDNDMSAyLjQ0NzcyIDEuNDQ3NzIgMiAyIDJMMTIgMkMxMi41NTIzIDIgMTMgMi40NDc3MiAxMyAzTDEzIDZDMTMgNi41NTIyOSAxMi41NTIzIDcgMTIgN0wyIDdaIiBmaWxsPSIjNjE2MTYxIi8+CjxkZWZzPgo8Y2xpcFBhdGggaWQ9ImNsaXAwXzEzN18xOTQ5OCI+CjxyZWN0IGNsYXNzPSJqcC1pY29uMyIgd2lkdGg9IjYiIGhlaWdodD0iNiIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0ibWF0cml4KDEgMS43NDg0NmUtMDcgMS43NDg0NmUtMDcgLTEgNCAxMy40NDQzKSIvPgo8L2NsaXBQYXRoPgo8L2RlZnM+Cjwvc3ZnPgo=);
  --jp-icon-add: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDEzaC02djZoLTJ2LTZINXYtMmg2VjVoMnY2aDZ2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bell: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE2IDE2IiB2ZXJzaW9uPSIxLjEiPgogICA8cGF0aCBjbGFzcz0ianAtaWNvbjIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMzMzMzMzIgogICAgICBkPSJtOCAwLjI5Yy0xLjQgMC0yLjcgMC43My0zLjYgMS44LTEuMiAxLjUtMS40IDMuNC0xLjUgNS4yLTAuMTggMi4yLTAuNDQgNC0yLjMgNS4zbDAuMjggMS4zaDVjMC4wMjYgMC42NiAwLjMyIDEuMSAwLjcxIDEuNSAwLjg0IDAuNjEgMiAwLjYxIDIuOCAwIDAuNTItMC40IDAuNi0xIDAuNzEtMS41aDVsMC4yOC0xLjNjLTEuOS0wLjk3LTIuMi0zLjMtMi4zLTUuMy0wLjEzLTEuOC0wLjI2LTMuNy0xLjUtNS4yLTAuODUtMS0yLjItMS44LTMuNi0xLjh6bTAgMS40YzAuODggMCAxLjkgMC41NSAyLjUgMS4zIDAuODggMS4xIDEuMSAyLjcgMS4yIDQuNCAwLjEzIDEuNyAwLjIzIDMuNiAxLjMgNS4yaC0xMGMxLjEtMS42IDEuMi0zLjQgMS4zLTUuMiAwLjEzLTEuNyAwLjMtMy4zIDEuMi00LjQgMC41OS0wLjcyIDEuNi0xLjMgMi41LTEuM3ptLTAuNzQgMTJoMS41Yy0wLjAwMTUgMC4yOCAwLjAxNSAwLjc5LTAuNzQgMC43OS0wLjczIDAuMDAxNi0wLjcyLTAuNTMtMC43NC0wLjc5eiIgLz4KPC9zdmc+Cg==);
  --jp-icon-bug-dot: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiPgogICAgICAgIDxwYXRoIGZpbGwtcnVsZT0iZXZlbm9kZCIgY2xpcC1ydWxlPSJldmVub2RkIiBkPSJNMTcuMTkgOEgyMFYxMEgxNy45MUMxNy45NiAxMC4zMyAxOCAxMC42NiAxOCAxMVYxMkgyMFYxNEgxOC41SDE4VjE0LjAyNzVDMTUuNzUgMTQuMjc2MiAxNCAxNi4xODM3IDE0IDE4LjVDMTQgMTkuMjA4IDE0LjE2MzUgMTkuODc3OSAxNC40NTQ5IDIwLjQ3MzlDMTMuNzA2MyAyMC44MTE3IDEyLjg3NTcgMjEgMTIgMjFDOS43OCAyMSA3Ljg1IDE5Ljc5IDYuODEgMThINFYxNkg2LjA5QzYuMDQgMTUuNjcgNiAxNS4zNCA2IDE1VjE0SDRWMTJINlYxMUM2IDEwLjY2IDYuMDQgMTAuMzMgNi4wOSAxMEg0VjhINi44MUM3LjI2IDcuMjIgNy44OCA2LjU1IDguNjIgNi4wNEw3IDQuNDFMOC40MSAzTDEwLjU5IDUuMTdDMTEuMDQgNS4wNiAxMS41MSA1IDEyIDVDMTIuNDkgNSAxMi45NiA1LjA2IDEzLjQyIDUuMTdMMTUuNTkgM0wxNyA0LjQxTDE1LjM3IDYuMDRDMTYuMTIgNi41NSAxNi43NCA3LjIyIDE3LjE5IDhaTTEwIDE2SDE0VjE0SDEwVjE2Wk0xMCAxMkgxNFYxMEgxMFYxMloiIGZpbGw9IiM2MTYxNjEiLz4KICAgICAgICA8cGF0aCBkPSJNMjIgMTguNUMyMiAyMC40MzMgMjAuNDMzIDIyIDE4LjUgMjJDMTYuNTY3IDIyIDE1IDIwLjQzMyAxNSAxOC41QzE1IDE2LjU2NyAxNi41NjcgMTUgMTguNSAxNUMyMC40MzMgMTUgMjIgMTYuNTY3IDIyIDE4LjVaIiBmaWxsPSIjNjE2MTYxIi8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bug: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0yMCA4aC0yLjgxYy0uNDUtLjc4LTEuMDctMS40NS0xLjgyLTEuOTZMMTcgNC40MSAxNS41OSAzbC0yLjE3IDIuMTdDMTIuOTYgNS4wNiAxMi40OSA1IDEyIDVjLS40OSAwLS45Ni4wNi0xLjQxLjE3TDguNDEgMyA3IDQuNDFsMS42MiAxLjYzQzcuODggNi41NSA3LjI2IDcuMjIgNi44MSA4SDR2MmgyLjA5Yy0uMDUuMzMtLjA5LjY2LS4wOSAxdjFINHYyaDJ2MWMwIC4zNC4wNC42Ny4wOSAxSDR2MmgyLjgxYzEuMDQgMS43OSAyLjk3IDMgNS4xOSAzczQuMTUtMS4yMSA1LjE5LTNIMjB2LTJoLTIuMDljLjA1LS4zMy4wOS0uNjYuMDktMXYtMWgydi0yaC0ydi0xYzAtLjM0LS4wNC0uNjctLjA5LTFIMjBWOHptLTYgOGgtNHYtMmg0djJ6bTAtNGgtNHYtMmg0djJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-build: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE0LjkgMTcuNDVDMTYuMjUgMTcuNDUgMTcuMzUgMTYuMzUgMTcuMzUgMTVDMTcuMzUgMTMuNjUgMTYuMjUgMTIuNTUgMTQuOSAxMi41NUMxMy41NCAxMi41NSAxMi40NSAxMy42NSAxMi40NSAxNUMxMi40NSAxNi4zNSAxMy41NCAxNy40NSAxNC45IDE3LjQ1Wk0yMC4xIDE1LjY4TDIxLjU4IDE2Ljg0QzIxLjcxIDE2Ljk1IDIxLjc1IDE3LjEzIDIxLjY2IDE3LjI5TDIwLjI2IDE5LjcxQzIwLjE3IDE5Ljg2IDIwIDE5LjkyIDE5LjgzIDE5Ljg2TDE4LjA5IDE5LjE2QzE3LjczIDE5LjQ0IDE3LjMzIDE5LjY3IDE2LjkxIDE5Ljg1TDE2LjY0IDIxLjdDMTYuNjIgMjEuODcgMTYuNDcgMjIgMTYuMyAyMkgxMy41QzEzLjMyIDIyIDEzLjE4IDIxLjg3IDEzLjE1IDIxLjdMMTIuODkgMTkuODVDMTIuNDYgMTkuNjcgMTIuMDcgMTkuNDQgMTEuNzEgMTkuMTZMOS45NjAwMiAxOS44NkM5LjgxMDAyIDE5LjkyIDkuNjIwMDIgMTkuODYgOS41NDAwMiAxOS43MUw4LjE0MDAyIDE3LjI5QzguMDUwMDIgMTcuMTMgOC4wOTAwMiAxNi45NSA4LjIyMDAyIDE2Ljg0TDkuNzAwMDIgMTUuNjhMOS42NTAwMSAxNUw5LjcwMDAyIDE0LjMxTDguMjIwMDIgMTMuMTZDOC4wOTAwMiAxMy4wNSA4LjA1MDAyIDEyLjg2IDguMTQwMDIgMTIuNzFMOS41NDAwMiAxMC4yOUM5LjYyMDAyIDEwLjEzIDkuODEwMDIgMTAuMDcgOS45NjAwMiAxMC4xM0wxMS43MSAxMC44NEMxMi4wNyAxMC41NiAxMi40NiAxMC4zMiAxMi44OSAxMC4xNUwxMy4xNSA4LjI4OTk4QzEzLjE4IDguMTI5OTggMTMuMzIgNy45OTk5OCAxMy41IDcuOTk5OThIMTYuM0MxNi40NyA3Ljk5OTk4IDE2LjYyIDguMTI5OTggMTYuNjQgOC4yODk5OEwxNi45MSAxMC4xNUMxNy4zMyAxMC4zMiAxNy43MyAxMC41NiAxOC4wOSAxMC44NEwxOS44MyAxMC4xM0MyMCAxMC4wNyAyMC4xNyAxMC4xMyAyMC4yNiAxMC4yOUwyMS42NiAxMi43MUMyMS43NSAxMi44NiAyMS43MSAxMy4wNSAyMS41OCAxMy4xNkwyMC4xIDE0LjMxTDIwLjE1IDE1TDIwLjEgMTUuNjhaIi8+CiAgICA8cGF0aCBkPSJNNy4zMjk2NiA3LjQ0NDU0QzguMDgzMSA3LjAwOTU0IDguMzM5MzIgNi4wNTMzMiA3LjkwNDMyIDUuMjk5ODhDNy40NjkzMiA0LjU0NjQzIDYuNTA4MSA0LjI4MTU2IDUuNzU0NjYgNC43MTY1NkM1LjM5MTc2IDQuOTI2MDggNS4xMjY5NSA1LjI3MTE4IDUuMDE4NDkgNS42NzU5NEM0LjkxMDA0IDYuMDgwNzEgNC45NjY4MiA2LjUxMTk4IDUuMTc2MzQgNi44NzQ4OEM1LjYxMTM0IDcuNjI4MzIgNi41NzYyMiA3Ljg3OTU0IDcuMzI5NjYgNy40NDQ1NFpNOS42NTcxOCA0Ljc5NTkzTDEwLjg2NzIgNC45NTE3OUMxMC45NjI4IDQuOTc3NDEgMTEuMDQwMiA1LjA3MTMzIDExLjAzODIgNS4xODc5M0wxMS4wMzg4IDYuOTg4OTNDMTEuMDQ1NSA3LjEwMDU0IDEwLjk2MTYgNy4xOTUxOCAxMC44NTUgNy4yMTA1NEw5LjY2MDAxIDcuMzgwODNMOS4yMzkxNSA4LjEzMTg4TDkuNjY5NjEgOS4yNTc0NUM5LjcwNzI5IDkuMzYyNzEgOS42NjkzNCA5LjQ3Njk5IDkuNTc0MDggOS41MzE5OUw4LjAxNTIzIDEwLjQzMkM3LjkxMTMxIDEwLjQ5MiA3Ljc5MzM3IDEwLjQ2NzcgNy43MjEwNSAxMC4zODI0TDYuOTg3NDggOS40MzE4OEw2LjEwOTMxIDkuNDMwODNMNS4zNDcwNCAxMC4zOTA1QzUuMjg5MDkgMTAuNDcwMiA1LjE3MzgzIDEwLjQ5MDUgNS4wNzE4NyAxMC40MzM5TDMuNTEyNDUgOS41MzI5M0MzLjQxMDQ5IDkuNDc2MzMgMy4zNzY0NyA5LjM1NzQxIDMuNDEwNzUgOS4yNTY3OUwzLjg2MzQ3IDguMTQwOTNMMy42MTc0OSA3Ljc3NDg4TDMuNDIzNDcgNy4zNzg4M0wyLjIzMDc1IDcuMjEyOTdDMi4xMjY0NyA3LjE5MjM1IDIuMDQwNDkgNy4xMDM0MiAyLjA0MjQ1IDYuOTg2ODJMMi4wNDE4NyA1LjE4NTgyQzIuMDQzODMgNS4wNjkyMiAyLjExOTA5IDQuOTc5NTggMi4yMTcwNCA0Ljk2OTIyTDMuNDIwNjUgNC43OTM5M0wzLjg2NzQ5IDQuMDI3ODhMMy40MTEwNSAyLjkxNzMxQzMuMzczMzcgMi44MTIwNCAzLjQxMTMxIDIuNjk3NzYgMy41MTUyMyAyLjYzNzc2TDUuMDc0MDggMS43Mzc3NkM1LjE2OTM0IDEuNjgyNzYgNS4yODcyOSAxLjcwNzA0IDUuMzU5NjEgMS43OTIzMUw2LjExOTE1IDIuNzI3ODhMNi45ODAwMSAyLjczODkzTDcuNzI0OTYgMS43ODkyMkM3Ljc5MTU2IDEuNzA0NTggNy45MTU0OCAxLjY3OTIyIDguMDA4NzkgMS43NDA4Mkw5LjU2ODIxIDIuNjQxODJDOS42NzAxNyAyLjY5ODQyIDkuNzEyODUgMi44MTIzNCA5LjY4NzIzIDIuOTA3OTdMOS4yMTcxOCA0LjAzMzgzTDkuNDYzMTYgNC4zOTk4OEw5LjY1NzE4IDQuNzk1OTNaIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iOS45LDEzLjYgMy42LDcuNCA0LjQsNi42IDkuOSwxMi4yIDE1LjQsNi43IDE2LjEsNy40ICIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNS45TDksOS43bDMuOC0zLjhsMS4yLDEuMmwtNC45LDVsLTQuOS01TDUuMiw1Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNy41TDksMTEuMmwzLjgtMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-left: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik0xMC44LDEyLjhMNy4xLDlsMy44LTMuOGwwLDcuNkgxMC44eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-right: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik03LjIsNS4yTDEwLjksOWwtMy44LDMuOFY1LjJINy4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-up-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iMTUuNCwxMy4zIDkuOSw3LjcgNC40LDEzLjIgMy42LDEyLjUgOS45LDYuMyAxNi4xLDEyLjYgIi8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-up: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik01LjIsMTAuNUw5LDYuOGwzLjgsMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-case-sensitive: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWFjY2VudDIiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTcuNiw4aDAuOWwzLjUsOGgtMS4xTDEwLDE0SDZsLTAuOSwySDRMNy42LDh6IE04LDkuMUw2LjQsMTNoMy4yTDgsOS4xeiIvPgogICAgPHBhdGggZD0iTTE2LjYsOS44Yy0wLjIsMC4xLTAuNCwwLjEtMC43LDAuMWMtMC4yLDAtMC40LTAuMS0wLjYtMC4yYy0wLjEtMC4xLTAuMi0wLjQtMC4yLTAuNyBjLTAuMywwLjMtMC42LDAuNS0wLjksMC43Yy0wLjMsMC4xLTAuNywwLjItMS4xLDAuMmMtMC4zLDAtMC41LDAtMC43LTAuMWMtMC4yLTAuMS0wLjQtMC4yLTAuNi0wLjNjLTAuMi0wLjEtMC4zLTAuMy0wLjQtMC41IGMtMC4xLTAuMi0wLjEtMC40LTAuMS0wLjdjMC0wLjMsMC4xLTAuNiwwLjItMC44YzAuMS0wLjIsMC4zLTAuNCwwLjQtMC41QzEyLDcsMTIuMiw2LjksMTIuNSw2LjhjMC4yLTAuMSwwLjUtMC4xLDAuNy0wLjIgYzAuMy0wLjEsMC41LTAuMSwwLjctMC4xYzAuMiwwLDAuNC0wLjEsMC42LTAuMWMwLjIsMCwwLjMtMC4xLDAuNC0wLjJjMC4xLTAuMSwwLjItMC4yLDAuMi0wLjRjMC0xLTEuMS0xLTEuMy0xIGMtMC40LDAtMS40LDAtMS40LDEuMmgtMC45YzAtMC40LDAuMS0wLjcsMC4yLTFjMC4xLTAuMiwwLjMtMC40LDAuNS0wLjZjMC4yLTAuMiwwLjUtMC4zLDAuOC0wLjNDMTMuMyw0LDEzLjYsNCwxMy45LDQgYzAuMywwLDAuNSwwLDAuOCwwLjFjMC4zLDAsMC41LDAuMSwwLjcsMC4yYzAuMiwwLjEsMC40LDAuMywwLjUsMC41QzE2LDUsMTYsNS4yLDE2LDUuNnYyLjljMCwwLjIsMCwwLjQsMCwwLjUgYzAsMC4xLDAuMSwwLjIsMC4zLDAuMmMwLjEsMCwwLjIsMCwwLjMsMFY5Ljh6IE0xNS4yLDYuOWMtMS4yLDAuNi0zLjEsMC4yLTMuMSwxLjRjMCwxLjQsMy4xLDEsMy4xLTAuNVY2Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik05IDE2LjE3TDQuODMgMTJsLTEuNDIgMS40MUw5IDE5IDIxIDdsLTEuNDEtMS40MXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-circle-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDJDNi40NyAyIDIgNi40NyAyIDEyczQuNDcgMTAgMTAgMTAgMTAtNC40NyAxMC0xMFMxNy41MyAyIDEyIDJ6bTAgMThjLTQuNDEgMC04LTMuNTktOC04czMuNTktOCA4LTggOCAzLjU5IDggOC0zLjU5IDgtOCA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iOSIgY3k9IjkiIHI9IjgiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-clear: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8bWFzayBpZD0iZG9udXRIb2xlIj4KICAgIDxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiIC8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSI4IiBmaWxsPSJibGFjayIvPgogIDwvbWFzaz4KCiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxyZWN0IGhlaWdodD0iMTgiIHdpZHRoPSIyIiB4PSIxMSIgeT0iMyIgdHJhbnNmb3JtPSJyb3RhdGUoMzE1LCAxMiwgMTIpIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgbWFzaz0idXJsKCNkb251dEhvbGUpIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-close: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1ub25lIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIGpwLWljb24zLWhvdmVyIiBmaWxsPSJub25lIj4KICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjExIi8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIGpwLWljb24tYWNjZW50Mi1ob3ZlciIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMTkgNi40MUwxNy41OSA1IDEyIDEwLjU5IDYuNDEgNSA1IDYuNDEgMTAuNTkgMTIgNSAxNy41OSA2LjQxIDE5IDEyIDEzLjQxIDE3LjU5IDE5IDE5IDE3LjU5IDEzLjQxIDEyeiIvPgogIDwvZz4KCiAgPGcgY2xhc3M9ImpwLWljb24tbm9uZSBqcC1pY29uLWJ1c3kiIGZpbGw9Im5vbmUiPgogICAgPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-code-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBzaGFwZS1yZW5kZXJpbmc9Imdlb21ldHJpY1ByZWNpc2lvbiI+CiAgICA8cGF0aCBkPSJNNi41OSwzLjQxTDIsOEw2LjU5LDEyLjZMOCwxMS4xOEw0LjgyLDhMOCw0LjgyTDYuNTksMy40MU0xMi40MSwzLjQxTDExLDQuODJMMTQuMTgsOEwxMSwxMS4xOEwxMi40MSwxMi42TDE3LDhMMTIuNDEsMy40MU0yMS41OSwxMS41OUwxMy41LDE5LjY4TDkuODMsMTZMOC40MiwxNy40MUwxMy41LDIyLjVMMjMsMTNMMjEuNTksMTEuNTlaIiAvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-code: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTExLjQgMTguNkw2LjggMTRMMTEuNCA5LjRMMTAgOEw0IDE0TDEwIDIwTDExLjQgMTguNlpNMTYuNiAxOC42TDIxLjIgMTRMMTYuNiA5LjRMMTggOEwyNCAxNEwxOCAyMEwxNi42IDE4LjZWMTguNloiLz4KCTwvZz4KPC9zdmc+Cg==);
  --jp-icon-collapse-all: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTggMmMxIDAgMTEgMCAxMiAwczIgMSAyIDJjMCAxIDAgMTEgMCAxMnMwIDItMiAyQzIwIDE0IDIwIDQgMjAgNFMxMCA0IDYgNGMwLTIgMS0yIDItMnoiIC8+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTE4IDhjMC0xLTEtMi0yLTJTNSA2IDQgNnMtMiAxLTIgMmMwIDEgMCAxMSAwIDEyczEgMiAyIDJjMSAwIDExIDAgMTIgMHMyLTEgMi0yYzAtMSAwLTExIDAtMTJ6bS0yIDB2MTJINFY4eiIgLz4KICAgICAgICA8cGF0aCBkPSJNNiAxM3YyaDh2LTJ6IiAvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-console: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwMCAyMDAiPgogIDxnIGNsYXNzPSJqcC1jb25zb2xlLWljb24tYmFja2dyb3VuZC1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMjg4RDEiPgogICAgPHBhdGggZD0iTTIwIDE5LjhoMTYwdjE1OS45SDIweiIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtY29uc29sZS1pY29uLWNvbG9yIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIj4KICAgIDxwYXRoIGQ9Ik0xMDUgMTI3LjNoNDB2MTIuOGgtNDB6TTUxLjEgNzdMNzQgOTkuOWwtMjMuMyAyMy4zIDEwLjUgMTAuNSAyMy4zLTIzLjNMOTUgOTkuOSA4NC41IDg5LjQgNjEuNiA2Ni41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-copy: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTExLjksMUgzLjJDMi40LDEsMS43LDEuNywxLjcsMi41djEwLjJoMS41VjIuNWg4LjdWMXogTTE0LjEsMy45aC04Yy0wLjgsMC0xLjUsMC43LTEuNSwxLjV2MTAuMmMwLDAuOCwwLjcsMS41LDEuNSwxLjVoOCBjMC44LDAsMS41LTAuNywxLjUtMS41VjUuNEMxNS41LDQuNiwxNC45LDMuOSwxNC4xLDMuOXogTTE0LjEsMTUuNWgtOFY1LjRoOFYxNS41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-copyright: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGVuYWJsZS1iYWNrZ3JvdW5kPSJuZXcgMCAwIDI0IDI0IiBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCI+CiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0xMS44OCw5LjE0YzEuMjgsMC4wNiwxLjYxLDEuMTUsMS42MywxLjY2aDEuNzljLTAuMDgtMS45OC0xLjQ5LTMuMTktMy40NS0zLjE5QzkuNjQsNy42MSw4LDksOCwxMi4xNCBjMCwxLjk0LDAuOTMsNC4yNCwzLjg0LDQuMjRjMi4yMiwwLDMuNDEtMS42NSwzLjQ0LTIuOTVoLTEuNzljLTAuMDMsMC41OS0wLjQ1LDEuMzgtMS42MywxLjQ0QzEwLjU1LDE0LjgzLDEwLDEzLjgxLDEwLDEyLjE0IEMxMCw5LjI1LDExLjI4LDkuMTYsMTEuODgsOS4xNHogTTEyLDJDNi40OCwyLDIsNi40OCwyLDEyczQuNDgsMTAsMTAsMTBzMTAtNC40OCwxMC0xMFMxNy41MiwyLDEyLDJ6IE0xMiwyMGMtNC40MSwwLTgtMy41OS04LTggczMuNTktOCw4LThzOCwzLjU5LDgsOFMxNi40MSwyMCwxMiwyMHoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-cut: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkuNjQgNy42NGMuMjMtLjUuMzYtMS4wNS4zNi0xLjY0IDAtMi4yMS0xLjc5LTQtNC00UzIgMy43OSAyIDZzMS43OSA0IDQgNGMuNTkgMCAxLjE0LS4xMyAxLjY0LS4zNkwxMCAxMmwtMi4zNiAyLjM2QzcuMTQgMTQuMTMgNi41OSAxNCA2IDE0Yy0yLjIxIDAtNCAxLjc5LTQgNHMxLjc5IDQgNCA0IDQtMS43OSA0LTRjMC0uNTktLjEzLTEuMTQtLjM2LTEuNjRMMTIgMTRsNyA3aDN2LTFMOS42NCA3LjY0ek02IDhjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTAgMTJjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTYtNy41Yy0uMjggMC0uNS0uMjItLjUtLjVzLjIyLS41LjUtLjUuNS4yMi41LjUtLjIyLjUtLjUuNXpNMTkgM2wtNiA2IDIgMiA3LTdWM3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-delete: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2cHgiIGhlaWdodD0iMTZweCI+CiAgICA8cGF0aCBkPSJNMCAwaDI0djI0SDB6IiBmaWxsPSJub25lIiAvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjI2MjYyIiBkPSJNNiAxOWMwIDEuMS45IDIgMiAyaDhjMS4xIDAgMi0uOSAyLTJWN0g2djEyek0xOSA0aC0zLjVsLTEtMWgtNWwtMSAxSDV2MmgxNFY0eiIgLz4KPC9zdmc+Cg==);
  --jp-icon-download: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDloLTRWM0g5djZINWw3IDcgNy03ek01IDE4djJoMTR2LTJINXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-duplicate: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiIGNsaXAtcnVsZT0iZXZlbm9kZCIgZD0iTTIuNzk5OTggMC44NzVIOC44OTU4MkM5LjIwMDYxIDAuODc1IDkuNDQ5OTggMS4xMzkxNCA5LjQ0OTk4IDEuNDYxOThDOS40NDk5OCAxLjc4NDgyIDkuMjAwNjEgMi4wNDg5NiA4Ljg5NTgyIDIuMDQ4OTZIMy4zNTQxNUMzLjA0OTM2IDIuMDQ4OTYgMi43OTk5OCAyLjMxMzEgMi43OTk5OCAyLjYzNTk0VjkuNjc5NjlDMi43OTk5OCAxMC4wMDI1IDIuNTUwNjEgMTAuMjY2NyAyLjI0NTgyIDEwLjI2NjdDMS45NDEwMyAxMC4yNjY3IDEuNjkxNjUgMTAuMDAyNSAxLjY5MTY1IDkuNjc5NjlWMi4wNDg5NkMxLjY5MTY1IDEuNDAzMjggMi4xOTA0IDAuODc1IDIuNzk5OTggMC44NzVaTTUuMzY2NjUgMTEuOVY0LjU1SDExLjA4MzNWMTEuOUg1LjM2NjY1Wk00LjE0MTY1IDQuMTQxNjdDNC4xNDE2NSAzLjY5MDYzIDQuNTA3MjggMy4zMjUgNC45NTgzMiAzLjMyNUgxMS40OTE3QzExLjk0MjcgMy4zMjUgMTIuMzA4MyAzLjY5MDYzIDEyLjMwODMgNC4xNDE2N1YxMi4zMDgzQzEyLjMwODMgMTIuNzU5NCAxMS45NDI3IDEzLjEyNSAxMS40OTE3IDEzLjEyNUg0Ljk1ODMyQzQuNTA3MjggMTMuMTI1IDQuMTQxNjUgMTIuNzU5NCA0LjE0MTY1IDEyLjMwODNWNC4xNDE2N1oiIGZpbGw9IiM2MTYxNjEiLz4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBkPSJNOS40MzU3NCA4LjI2NTA3SDguMzY0MzFWOS4zMzY1QzguMzY0MzEgOS40NTQzNSA4LjI2Nzg4IDkuNTUwNzggOC4xNTAwMiA5LjU1MDc4QzguMDMyMTcgOS41NTA3OCA3LjkzNTc0IDkuNDU0MzUgNy45MzU3NCA5LjMzNjVWOC4yNjUwN0g2Ljg2NDMxQzYuNzQ2NDUgOC4yNjUwNyA2LjY1MDAyIDguMTY4NjQgNi42NTAwMiA4LjA1MDc4QzYuNjUwMDIgNy45MzI5MiA2Ljc0NjQ1IDcuODM2NSA2Ljg2NDMxIDcuODM2NUg3LjkzNTc0VjYuNzY1MDdDNy45MzU3NCA2LjY0NzIxIDguMDMyMTcgNi41NTA3OCA4LjE1MDAyIDYuNTUwNzhDOC4yNjc4OCA2LjU1MDc4IDguMzY0MzEgNi42NDcyMSA4LjM2NDMxIDYuNzY1MDdWNy44MzY1SDkuNDM1NzRDOS41NTM2IDcuODM2NSA5LjY1MDAyIDcuOTMyOTIgOS42NTAwMiA4LjA1MDc4QzkuNjUwMDIgOC4xNjg2NCA5LjU1MzYgOC4yNjUwNyA5LjQzNTc0IDguMjY1MDdaIiBmaWxsPSIjNjE2MTYxIiBzdHJva2U9IiM2MTYxNjEiIHN0cm9rZS13aWR0aD0iMC41Ii8+Cjwvc3ZnPgo=);
  --jp-icon-edit: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMgMTcuMjVWMjFoMy43NUwxNy44MSA5Ljk0bC0zLjc1LTMuNzVMMyAxNy4yNXpNMjAuNzEgNy4wNGMuMzktLjM5LjM5LTEuMDIgMC0xLjQxbC0yLjM0LTIuMzRjLS4zOS0uMzktMS4wMi0uMzktMS40MSAwbC0xLjgzIDEuODMgMy43NSAzLjc1IDEuODMtMS44M3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-ellipses: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iNSIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxOSIgY3k9IjEyIiByPSIyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-error: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj48Y2lyY2xlIGN4PSIxMiIgY3k9IjE5IiByPSIyIi8+PHBhdGggZD0iTTEwIDNoNHYxMmgtNHoiLz48L2c+CjxwYXRoIGZpbGw9Im5vbmUiIGQ9Ik0wIDBoMjR2MjRIMHoiLz4KPC9zdmc+Cg==);
  --jp-icon-expand-all: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTggMmMxIDAgMTEgMCAxMiAwczIgMSAyIDJjMCAxIDAgMTEgMCAxMnMwIDItMiAyQzIwIDE0IDIwIDQgMjAgNFMxMCA0IDYgNGMwLTIgMS0yIDItMnoiIC8+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTE4IDhjMC0xLTEtMi0yLTJTNSA2IDQgNnMtMiAxLTIgMmMwIDEgMCAxMSAwIDEyczEgMiAyIDJjMSAwIDExIDAgMTIgMHMyLTEgMi0yYzAtMSAwLTExIDAtMTJ6bS0yIDB2MTJINFY4eiIgLz4KICAgICAgICA8cGF0aCBkPSJNMTEgMTBIOXYzSDZ2MmgzdjNoMnYtM2gzdi0yaC0zeiIgLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-extension: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwLjUgMTFIMTlWN2MwLTEuMS0uOS0yLTItMmgtNFYzLjVDMTMgMi4xMiAxMS44OCAxIDEwLjUgMVM4IDIuMTIgOCAzLjVWNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAydjMuOEgzLjVjMS40OSAwIDIuNyAxLjIxIDIuNyAyLjdzLTEuMjEgMi43LTIuNyAyLjdIMlYyMGMwIDEuMS45IDIgMiAyaDMuOHYtMS41YzAtMS40OSAxLjIxLTIuNyAyLjctMi43IDEuNDkgMCAyLjcgMS4yMSAyLjcgMi43VjIySDE3YzEuMSAwIDItLjkgMi0ydi00aDEuNWMxLjM4IDAgMi41LTEuMTIgMi41LTIuNVMyMS44OCAxMSAyMC41IDExeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-fast-forward: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTQgMThsOC41LTZMNCA2djEyem05LTEydjEybDguNS02TDEzIDZ6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-file-upload: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTZoNnYtNmg0bC03LTctNyA3aDR6bS00IDJoMTR2Mkg1eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-file: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuMyA4LjJsLTUuNS01LjVjLS4zLS4zLS43LS41LTEuMi0uNUgzLjljLS44LjEtMS42LjktMS42IDEuOHYxNC4xYzAgLjkuNyAxLjYgMS42IDEuNmgxNC4yYy45IDAgMS42LS43IDEuNi0xLjZWOS40Yy4xLS41LS4xLS45LS40LTEuMnptLTUuOC0zLjNsMy40IDMuNmgtMy40VjQuOXptMy45IDEyLjdINC43Yy0uMSAwLS4yIDAtLjItLjJWNC43YzAtLjIuMS0uMy4yLS4zaDcuMnY0LjRzMCAuOC4zIDEuMWMuMy4zIDEuMS4zIDEuMS4zaDQuM3Y3LjJzLS4xLjItLjIuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-filter-dot: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTE0LDEyVjE5Ljg4QzE0LjA0LDIwLjE4IDEzLjk0LDIwLjUgMTMuNzEsMjAuNzFDMTMuMzIsMjEuMSAxMi42OSwyMS4xIDEyLjMsMjAuNzFMMTAuMjksMTguN0MxMC4wNiwxOC40NyA5Ljk2LDE4LjE2IDEwLDE3Ljg3VjEySDkuOTdMNC4yMSw0LjYyQzMuODcsNC4xOSAzLjk1LDMuNTYgNC4zOCwzLjIyQzQuNTcsMy4wOCA0Ljc4LDMgNSwzVjNIMTlWM0MxOS4yMiwzIDE5LjQzLDMuMDggMTkuNjIsMy4yMkMyMC4wNSwzLjU2IDIwLjEzLDQuMTkgMTkuNzksNC42MkwxNC4wMywxMkgxNFoiIC8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWRvdCIgZmlsbD0iI0ZGRiI+CiAgICA8Y2lyY2xlIGN4PSIxOCIgY3k9IjE3IiByPSIzIj48L2NpcmNsZT4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-filter-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEwIDE4aDR2LTJoLTR2MnpNMyA2djJoMThWNkgzem0zIDdoMTJ2LTJINnYyeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-filter: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTE0LDEyVjE5Ljg4QzE0LjA0LDIwLjE4IDEzLjk0LDIwLjUgMTMuNzEsMjAuNzFDMTMuMzIsMjEuMSAxMi42OSwyMS4xIDEyLjMsMjAuNzFMMTAuMjksMTguN0MxMC4wNiwxOC40NyA5Ljk2LDE4LjE2IDEwLDE3Ljg3VjEySDkuOTdMNC4yMSw0LjYyQzMuODcsNC4xOSAzLjk1LDMuNTYgNC4zOCwzLjIyQzQuNTcsMy4wOCA0Ljc4LDMgNSwzVjNIMTlWM0MxOS4yMiwzIDE5LjQzLDMuMDggMTkuNjIsMy4yMkMyMC4wNSwzLjU2IDIwLjEzLDQuMTkgMTkuNzksNC42MkwxNC4wMywxMkgxNFoiIC8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-folder-favorite: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjRweCIgdmlld0JveD0iMCAwIDI0IDI0IiB3aWR0aD0iMjRweCIgZmlsbD0iIzAwMDAwMCI+CiAgPHBhdGggZD0iTTAgMGgyNHYyNEgwVjB6IiBmaWxsPSJub25lIi8+PHBhdGggY2xhc3M9ImpwLWljb24zIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxNjE2MSIgZD0iTTIwIDZoLThsLTItMkg0Yy0xLjEgMC0yIC45LTIgMnYxMmMwIDEuMS45IDIgMiAyaDE2YzEuMSAwIDItLjkgMi0yVjhjMC0xLjEtLjktMi0yLTJ6bS0yLjA2IDExTDE1IDE1LjI4IDEyLjA2IDE3bC43OC0zLjMzLTIuNTktMi4yNCAzLjQxLS4yOUwxNSA4bDEuMzQgMy4xNCAzLjQxLjI5LTIuNTkgMi4yNC43OCAzLjMzeiIvPgo8L3N2Zz4K);
  --jp-icon-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY4YzAtMS4xLS45LTItMi0yaC04bC0yLTJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-home: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjRweCIgdmlld0JveD0iMCAwIDI0IDI0IiB3aWR0aD0iMjRweCIgZmlsbD0iIzAwMDAwMCI+CiAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPjxwYXRoIGNsYXNzPSJqcC1pY29uMyBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xMCAyMHYtNmg0djZoNXYtOGgzTDEyIDMgMiAxMmgzdjh6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-html5: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMDAiIGQ9Ik0xMDguNCAwaDIzdjIyLjhoMjEuMlYwaDIzdjY5aC0yM1Y0NmgtMjF2MjNoLTIzLjJNMjA2IDIzaC0yMC4zVjBoNjMuN3YyM0gyMjl2NDZoLTIzbTUzLjUtNjloMjQuMWwxNC44IDI0LjNMMzEzLjIgMGgyNC4xdjY5aC0yM1YzNC44bC0xNi4xIDI0LjgtMTYuMS0yNC44VjY5aC0yMi42bTg5LjItNjloMjN2NDYuMmgzMi42VjY5aC01NS42Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2U0NGQyNiIgZD0iTTEwNy42IDQ3MWwtMzMtMzcwLjRoMzYyLjhsLTMzIDM3MC4yTDI1NS43IDUxMiIvPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNmMTY1MjkiIGQ9Ik0yNTYgNDgwLjVWMTMxaDE0OC4zTDM3NiA0NDciLz4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNlYmViZWIiIGQ9Ik0xNDIgMTc2LjNoMTE0djQ1LjRoLTY0LjJsNC4yIDQ2LjVoNjB2NDUuM0gxNTQuNG0yIDIyLjhIMjAybDMuMiAzNi4zIDUwLjggMTMuNnY0Ny40bC05My4yLTI2Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIiBkPSJNMzY5LjYgMTc2LjNIMjU1Ljh2NDUuNGgxMDkuNm0tNC4xIDQ2LjVIMjU1Ljh2NDUuNGg1NmwtNS4zIDU5LTUwLjcgMTMuNnY0Ny4ybDkzLTI1LjgiLz4KPC9zdmc+Cg==);
  --jp-icon-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1icmFuZDQganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNGRkYiIGQ9Ik0yLjIgMi4yaDE3LjV2MTcuNUgyLjJ6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzNGNTFCNSIgZD0iTTIuMiAyLjJ2MTcuNWgxNy41bC4xLTE3LjVIMi4yem0xMi4xIDIuMmMxLjIgMCAyLjIgMSAyLjIgMi4ycy0xIDIuMi0yLjIgMi4yLTIuMi0xLTIuMi0yLjIgMS0yLjIgMi4yLTIuMnpNNC40IDE3LjZsMy4zLTguOCAzLjMgNi42IDIuMi0zLjIgNC40IDUuNEg0LjR6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-info: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUwLjk3OCA1MC45NzgiPgoJPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KCQk8cGF0aCBkPSJNNDMuNTIsNy40NThDMzguNzExLDIuNjQ4LDMyLjMwNywwLDI1LjQ4OSwwQzE4LjY3LDAsMTIuMjY2LDIuNjQ4LDcuNDU4LDcuNDU4CgkJCWMtOS45NDMsOS45NDEtOS45NDMsMjYuMTE5LDAsMzYuMDYyYzQuODA5LDQuODA5LDExLjIxMiw3LjQ1NiwxOC4wMzEsNy40NThjMCwwLDAuMDAxLDAsMC4wMDIsMAoJCQljNi44MTYsMCwxMy4yMjEtMi42NDgsMTguMDI5LTcuNDU4YzQuODA5LTQuODA5LDcuNDU3LTExLjIxMiw3LjQ1Ny0xOC4wM0M1MC45NzcsMTguNjcsNDguMzI4LDEyLjI2Niw0My41Miw3LjQ1OHoKCQkJIE00Mi4xMDYsNDIuMTA1Yy00LjQzMiw0LjQzMS0xMC4zMzIsNi44NzItMTYuNjE1LDYuODcyaC0wLjAwMmMtNi4yODUtMC4wMDEtMTIuMTg3LTIuNDQxLTE2LjYxNy02Ljg3MgoJCQljLTkuMTYyLTkuMTYzLTkuMTYyLTI0LjA3MSwwLTMzLjIzM0MxMy4zMDMsNC40NCwxOS4yMDQsMiwyNS40ODksMmM2LjI4NCwwLDEyLjE4NiwyLjQ0LDE2LjYxNyw2Ljg3MgoJCQljNC40MzEsNC40MzEsNi44NzEsMTAuMzMyLDYuODcxLDE2LjYxN0M0OC45NzcsMzEuNzcyLDQ2LjUzNiwzNy42NzUsNDIuMTA2LDQyLjEwNXoiLz4KCQk8cGF0aCBkPSJNMjMuNTc4LDMyLjIxOGMtMC4wMjMtMS43MzQsMC4xNDMtMy4wNTksMC40OTYtMy45NzJjMC4zNTMtMC45MTMsMS4xMS0xLjk5NywyLjI3Mi0zLjI1MwoJCQljMC40NjgtMC41MzYsMC45MjMtMS4wNjIsMS4zNjctMS41NzVjMC42MjYtMC43NTMsMS4xMDQtMS40NzgsMS40MzYtMi4xNzVjMC4zMzEtMC43MDcsMC40OTUtMS41NDEsMC40OTUtMi41CgkJCWMwLTEuMDk2LTAuMjYtMi4wODgtMC43NzktMi45NzljLTAuNTY1LTAuODc5LTEuNTAxLTEuMzM2LTIuODA2LTEuMzY5Yy0xLjgwMiwwLjA1Ny0yLjk4NSwwLjY2Ny0zLjU1LDEuODMyCgkJCWMtMC4zMDEsMC41MzUtMC41MDMsMS4xNDEtMC42MDcsMS44MTRjLTAuMTM5LDAuNzA3LTAuMjA3LDEuNDMyLTAuMjA3LDIuMTc0aC0yLjkzN2MtMC4wOTEtMi4yMDgsMC40MDctNC4xMTQsMS40OTMtNS43MTkKCQkJYzEuMDYyLTEuNjQsMi44NTUtMi40ODEsNS4zNzgtMi41MjdjMi4xNiwwLjAyMywzLjg3NCwwLjYwOCw1LjE0MSwxLjc1OGMxLjI3OCwxLjE2LDEuOTI5LDIuNzY0LDEuOTUsNC44MTEKCQkJYzAsMS4xNDItMC4xMzcsMi4xMTEtMC40MSwyLjkxMWMtMC4zMDksMC44NDUtMC43MzEsMS41OTMtMS4yNjgsMi4yNDNjLTAuNDkyLDAuNjUtMS4wNjgsMS4zMTgtMS43MywyLjAwMgoJCQljLTAuNjUsMC42OTctMS4zMTMsMS40NzktMS45ODcsMi4zNDZjLTAuMjM5LDAuMzc3LTAuNDI5LDAuNzc3LTAuNTY1LDEuMTk5Yy0wLjE2LDAuOTU5LTAuMjE3LDEuOTUxLTAuMTcxLDIuOTc5CgkJCUMyNi41ODksMzIuMjE4LDIzLjU3OCwzMi4yMTgsMjMuNTc4LDMyLjIxOHogTTIzLjU3OCwzOC4yMnYtMy40ODRoMy4wNzZ2My40ODRIMjMuNTc4eiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-inspector: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaW5zcGVjdG9yLWljb24tY29sb3IganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY2YzAtMS4xLS45LTItMi0yem0tNSAxNEg0di00aDExdjR6bTAtNUg0VjloMTF2NHptNSA1aC00VjloNHY5eiIvPgo8L3N2Zz4K);
  --jp-icon-json: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtanNvbi1pY29uLWNvbG9yIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI0Y5QTgyNSI+CiAgICA8cGF0aCBkPSJNMjAuMiAxMS44Yy0xLjYgMC0xLjcuNS0xLjcgMSAwIC40LjEuOS4xIDEuMy4xLjUuMS45LjEgMS4zIDAgMS43LTEuNCAyLjMtMy41IDIuM2gtLjl2LTEuOWguNWMxLjEgMCAxLjQgMCAxLjQtLjggMC0uMyAwLS42LS4xLTEgMC0uNC0uMS0uOC0uMS0xLjIgMC0xLjMgMC0xLjggMS4zLTItMS4zLS4yLTEuMy0uNy0xLjMtMiAwLS40LjEtLjguMS0xLjIuMS0uNC4xLS43LjEtMSAwLS44LS40LS43LTEuNC0uOGgtLjVWNC4xaC45YzIuMiAwIDMuNS43IDMuNSAyLjMgMCAuNC0uMS45LS4xIDEuMy0uMS41LS4xLjktLjEgMS4zIDAgLjUuMiAxIDEuNyAxdjEuOHpNMS44IDEwLjFjMS42IDAgMS43LS41IDEuNy0xIDAtLjQtLjEtLjktLjEtMS4zLS4xLS41LS4xLS45LS4xLTEuMyAwLTEuNiAxLjQtMi4zIDMuNS0yLjNoLjl2MS45aC0uNWMtMSAwLTEuNCAwLTEuNC44IDAgLjMgMCAuNi4xIDEgMCAuMi4xLjYuMSAxIDAgMS4zIDAgMS44LTEuMyAyQzYgMTEuMiA2IDExLjcgNiAxM2MwIC40LS4xLjgtLjEgMS4yLS4xLjMtLjEuNy0uMSAxIDAgLjguMy44IDEuNC44aC41djEuOWgtLjljLTIuMSAwLTMuNS0uNi0zLjUtMi4zIDAtLjQuMS0uOS4xLTEuMy4xLS41LjEtLjkuMS0xLjMgMC0uNS0uMi0xLTEuNy0xdi0xLjl6Ii8+CiAgICA8Y2lyY2xlIGN4PSIxMSIgY3k9IjEzLjgiIHI9IjIuMSIvPgogICAgPGNpcmNsZSBjeD0iMTEiIGN5PSI4LjIiIHI9IjIuMSIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-julia: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDMyNSAzMDAiPgogIDxnIGNsYXNzPSJqcC1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjY2IzYzMzIj4KICAgIDxwYXRoIGQ9Ik0gMTUwLjg5ODQzOCAyMjUgQyAxNTAuODk4NDM4IDI2Ni40MjE4NzUgMTE3LjMyMDMxMiAzMDAgNzUuODk4NDM4IDMwMCBDIDM0LjQ3NjU2MiAzMDAgMC44OTg0MzggMjY2LjQyMTg3NSAwLjg5ODQzOCAyMjUgQyAwLjg5ODQzOCAxODMuNTc4MTI1IDM0LjQ3NjU2MiAxNTAgNzUuODk4NDM4IDE1MCBDIDExNy4zMjAzMTIgMTUwIDE1MC44OTg0MzggMTgzLjU3ODEyNSAxNTAuODk4NDM4IDIyNSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzM4OTgyNiI+CiAgICA8cGF0aCBkPSJNIDIzNy41IDc1IEMgMjM3LjUgMTE2LjQyMTg3NSAyMDMuOTIxODc1IDE1MCAxNjIuNSAxNTAgQyAxMjEuMDc4MTI1IDE1MCA4Ny41IDExNi40MjE4NzUgODcuNSA3NSBDIDg3LjUgMzMuNTc4MTI1IDEyMS4wNzgxMjUgMCAxNjIuNSAwIEMgMjAzLjkyMTg3NSAwIDIzNy41IDMzLjU3ODEyNSAyMzcuNSA3NSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzk1NThiMiI+CiAgICA8cGF0aCBkPSJNIDMyNC4xMDE1NjIgMjI1IEMgMzI0LjEwMTU2MiAyNjYuNDIxODc1IDI5MC41MjM0MzggMzAwIDI0OS4xMDE1NjIgMzAwIEMgMjA3LjY3OTY4OCAzMDAgMTc0LjEwMTU2MiAyNjYuNDIxODc1IDE3NC4xMDE1NjIgMjI1IEMgMTc0LjEwMTU2MiAxODMuNTc4MTI1IDIwNy42Nzk2ODggMTUwIDI0OS4xMDE1NjIgMTUwIEMgMjkwLjUyMzQzOCAxNTAgMzI0LjEwMTU2MiAxODMuNTc4MTI1IDMyNC4xMDE1NjIgMjI1Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-jupyter-favicon: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTUyIiBoZWlnaHQ9IjE2NSIgdmlld0JveD0iMCAwIDE1MiAxNjUiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgPGcgY2xhc3M9ImpwLWp1cHl0ZXItaWNvbi1jb2xvciIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA3ODk0NywgMTEwLjU4MjkyNykiIGQ9Ik03NS45NDIyODQyLDI5LjU4MDQ1NjEgQzQzLjMwMjM5NDcsMjkuNTgwNDU2MSAxNC43OTY3ODMyLDE3LjY1MzQ2MzQgMCwwIEM1LjUxMDgzMjExLDE1Ljg0MDY4MjkgMTUuNzgxNTM4OSwyOS41NjY3NzMyIDI5LjM5MDQ5NDcsMzkuMjc4NDE3MSBDNDIuOTk5Nyw0OC45ODk4NTM3IDU5LjI3MzcsNTQuMjA2NzgwNSA3NS45NjA1Nzg5LDU0LjIwNjc4MDUgQzkyLjY0NzQ1NzksNTQuMjA2NzgwNSAxMDguOTIxNDU4LDQ4Ljk4OTg1MzcgMTIyLjUzMDY2MywzOS4yNzg0MTcxIEMxMzYuMTM5NDUzLDI5LjU2Njc3MzIgMTQ2LjQxMDI4NCwxNS44NDA2ODI5IDE1MS45MjExNTgsMCBDMTM3LjA4Nzg2OCwxNy42NTM0NjM0IDEwOC41ODI1ODksMjkuNTgwNDU2MSA3NS45NDIyODQyLDI5LjU4MDQ1NjEgTDc1Ljk0MjI4NDIsMjkuNTgwNDU2MSBaIiAvPgogICAgPHBhdGggdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMzczNjgsIDAuNzA0ODc4KSIgZD0iTTc1Ljk3ODQ1NzksMjQuNjI2NDA3MyBDMTA4LjYxODc2MywyNC42MjY0MDczIDEzNy4xMjQ0NTgsMzYuNTUzNDQxNSAxNTEuOTIxMTU4LDU0LjIwNjc4MDUgQzE0Ni40MTAyODQsMzguMzY2MjIyIDEzNi4xMzk0NTMsMjQuNjQwMTMxNyAxMjIuNTMwNjYzLDE0LjkyODQ4NzggQzEwOC45MjE0NTgsNS4yMTY4NDM5IDkyLjY0NzQ1NzksMCA3NS45NjA1Nzg5LDAgQzU5LjI3MzcsMCA0Mi45OTk3LDUuMjE2ODQzOSAyOS4zOTA0OTQ3LDE0LjkyODQ4NzggQzE1Ljc4MTUzODksMjQuNjQwMTMxNyA1LjUxMDgzMjExLDM4LjM2NjIyMiAwLDU0LjIwNjc4MDUgQzE0LjgzMzA4MTYsMzYuNTg5OTI5MyA0My4zMzg1Njg0LDI0LjYyNjQwNzMgNzUuOTc4NDU3OSwyNC42MjY0MDczIEw3NS45Nzg0NTc5LDI0LjYyNjQwNzMgWiIgLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzkiIGhlaWdodD0iNTEiIHZpZXdCb3g9IjAgMCAzOSA1MSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTYzOCAtMjI4MSkiPgogICAgIDxnIGNsYXNzPSJqcC1qdXB5dGVyLWljb24tY29sb3IiIGZpbGw9IiNGMzc3MjYiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5Ljc0IDIzMTEuOTgpIiBkPSJNIDE4LjI2NDYgNy4xMzQxMUMgMTAuNDE0NSA3LjEzNDExIDMuNTU4NzIgNC4yNTc2IDAgMEMgMS4zMjUzOSAzLjgyMDQgMy43OTU1NiA3LjEzMDgxIDcuMDY4NiA5LjQ3MzAzQyAxMC4zNDE3IDExLjgxNTIgMTQuMjU1NyAxMy4wNzM0IDE4LjI2OSAxMy4wNzM0QyAyMi4yODIzIDEzLjA3MzQgMjYuMTk2MyAxMS44MTUyIDI5LjQ2OTQgOS40NzMwM0MgMzIuNzQyNCA3LjEzMDgxIDM1LjIxMjYgMy44MjA0IDM2LjUzOCAwQyAzMi45NzA1IDQuMjU3NiAyNi4xMTQ4IDcuMTM0MTEgMTguMjY0NiA3LjEzNDExWiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5LjczIDIyODUuNDgpIiBkPSJNIDE4LjI3MzMgNS45MzkzMUMgMjYuMTIzNSA1LjkzOTMxIDMyLjk3OTMgOC44MTU4MyAzNi41MzggMTMuMDczNEMgMzUuMjEyNiA5LjI1MzAzIDMyLjc0MjQgNS45NDI2MiAyOS40Njk0IDMuNjAwNEMgMjYuMTk2MyAxLjI1ODE4IDIyLjI4MjMgMCAxOC4yNjkgMEMgMTQuMjU1NyAwIDEwLjM0MTcgMS4yNTgxOCA3LjA2ODYgMy42MDA0QyAzLjc5NTU2IDUuOTQyNjIgMS4zMjUzOSA5LjI1MzAzIDAgMTMuMDczNEMgMy41Njc0NSA4LjgyNDYzIDEwLjQyMzIgNS45MzkzMSAxOC4yNzMzIDUuOTM5MzFaIi8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjY5LjMgMjI4MS4zMSkiIGQ9Ik0gNS44OTM1MyAyLjg0NEMgNS45MTg4OSAzLjQzMTY1IDUuNzcwODUgNC4wMTM2NyA1LjQ2ODE1IDQuNTE2NDVDIDUuMTY1NDUgNS4wMTkyMiA0LjcyMTY4IDUuNDIwMTUgNC4xOTI5OSA1LjY2ODUxQyAzLjY2NDMgNS45MTY4OCAzLjA3NDQ0IDYuMDAxNTEgMi40OTgwNSA1LjkxMTcxQyAxLjkyMTY2IDUuODIxOSAxLjM4NDYzIDUuNTYxNyAwLjk1NDg5OCA1LjE2NDAxQyAwLjUyNTE3IDQuNzY2MzMgMC4yMjIwNTYgNC4yNDkwMyAwLjA4MzkwMzcgMy42Nzc1N0MgLTAuMDU0MjQ4MyAzLjEwNjExIC0wLjAyMTIzIDIuNTA2MTcgMC4xNzg3ODEgMS45NTM2NEMgMC4zNzg3OTMgMS40MDExIDAuNzM2ODA5IDAuOTIwODE3IDEuMjA3NTQgMC41NzM1MzhDIDEuNjc4MjYgMC4yMjYyNTkgMi4yNDA1NSAwLjAyNzU5MTkgMi44MjMyNiAwLjAwMjY3MjI5QyAzLjYwMzg5IC0wLjAzMDcxMTUgNC4zNjU3MyAwLjI0OTc4OSA0Ljk0MTQyIDAuNzgyNTUxQyA1LjUxNzExIDEuMzE1MzEgNS44NTk1NiAyLjA1Njc2IDUuODkzNTMgMi44NDRaIi8+CiAgICAgIDxwYXRoIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE2MzkuOCAyMzIzLjgxKSIgZD0iTSA3LjQyNzg5IDMuNTgzMzhDIDcuNDYwMDggNC4zMjQzIDcuMjczNTUgNS4wNTgxOSA2Ljg5MTkzIDUuNjkyMTNDIDYuNTEwMzEgNi4zMjYwNyA1Ljk1MDc1IDYuODMxNTYgNS4yODQxMSA3LjE0NDZDIDQuNjE3NDcgNy40NTc2MyAzLjg3MzcxIDcuNTY0MTQgMy4xNDcwMiA3LjQ1MDYzQyAyLjQyMDMyIDcuMzM3MTIgMS43NDMzNiA3LjAwODcgMS4yMDE4NCA2LjUwNjk1QyAwLjY2MDMyOCA2LjAwNTIgMC4yNzg2MSA1LjM1MjY4IDAuMTA1MDE3IDQuNjMyMDJDIC0wLjA2ODU3NTcgMy45MTEzNSAtMC4wMjYyMzYxIDMuMTU0OTQgMC4yMjY2NzUgMi40NTg1NkMgMC40Nzk1ODcgMS43NjIxNyAwLjkzMTY5NyAxLjE1NzEzIDEuNTI1NzYgMC43MjAwMzNDIDIuMTE5ODMgMC4yODI5MzUgMi44MjkxNCAwLjAzMzQzOTUgMy41NjM4OSAwLjAwMzEzMzQ0QyA0LjU0NjY3IC0wLjAzNzQwMzMgNS41MDUyOSAwLjMxNjcwNiA2LjIyOTYxIDAuOTg3ODM1QyA2Ljk1MzkzIDEuNjU4OTYgNy4zODQ4NCAyLjU5MjM1IDcuNDI3ODkgMy41ODMzOEwgNy40Mjc4OSAzLjU4MzM4WiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM4LjM2IDIyODYuMDYpIiBkPSJNIDIuMjc0NzEgNC4zOTYyOUMgMS44NDM2MyA0LjQxNTA4IDEuNDE2NzEgNC4zMDQ0NSAxLjA0Nzk5IDQuMDc4NDNDIDAuNjc5MjY4IDMuODUyNCAwLjM4NTMyOCAzLjUyMTE0IDAuMjAzMzcxIDMuMTI2NTZDIDAuMDIxNDEzNiAyLjczMTk4IC0wLjA0MDM3OTggMi4yOTE4MyAwLjAyNTgxMTYgMS44NjE4MUMgMC4wOTIwMDMxIDEuNDMxOCAwLjI4MzIwNCAxLjAzMTI2IDAuNTc1MjEzIDAuNzEwODgzQyAwLjg2NzIyMiAwLjM5MDUxIDEuMjQ2OTEgMC4xNjQ3MDggMS42NjYyMiAwLjA2MjA1OTJDIDIuMDg1NTMgLTAuMDQwNTg5NyAyLjUyNTYxIC0wLjAxNTQ3MTQgMi45MzA3NiAwLjEzNDIzNUMgMy4zMzU5MSAwLjI4Mzk0MSAzLjY4NzkyIDAuNTUxNTA1IDMuOTQyMjIgMC45MDMwNkMgNC4xOTY1MiAxLjI1NDYyIDQuMzQxNjkgMS42NzQzNiA0LjM1OTM1IDIuMTA5MTZDIDQuMzgyOTkgMi42OTEwNyA0LjE3Njc4IDMuMjU4NjkgMy43ODU5NyAzLjY4NzQ2QyAzLjM5NTE2IDQuMTE2MjQgMi44NTE2NiA0LjM3MTE2IDIuMjc0NzEgNC4zOTYyOUwgMi4yNzQ3MSA0LjM5NjI5WiIvPgogICAgPC9nPgogIDwvZz4+Cjwvc3ZnPgo=);
  --jp-icon-jupyterlab-wordmark: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMDAiIHZpZXdCb3g9IjAgMCAxODYwLjggNDc1Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0RTRFNEUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ4MC4xMzY0MDEsIDY0LjI3MTQ5MykiPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMDAwMDAsIDU4Ljg3NTU2NikiPgogICAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA4NzYwMywgMC4xNDAyOTQpIj4KICAgICAgICA8cGF0aCBkPSJNLTQyNi45LDE2OS44YzAsNDguNy0zLjcsNjQuNy0xMy42LDc2LjRjLTEwLjgsMTAtMjUsMTUuNS0zOS43LDE1LjVsMy43LDI5IGMyMi44LDAuMyw0NC44LTcuOSw2MS45LTIzLjFjMTcuOC0xOC41LDI0LTQ0LjEsMjQtODMuM1YwSC00Mjd2MTcwLjFMLTQyNi45LDE2OS44TC00MjYuOSwxNjkuOHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1LjA0NTI5NiwgNTYuODM3MTA0KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuNTYyNDUzLCAxLjc5OTg0MikiPgogICAgICAgIDxwYXRoIGQ9Ik0tMzEyLDE0OGMwLDIxLDAsMzkuNSwxLjcsNTUuNGgtMzEuOGwtMi4xLTMzLjNoLTAuOGMtNi43LDExLjYtMTYuNCwyMS4zLTI4LDI3LjkgYy0xMS42LDYuNi0yNC44LDEwLTM4LjIsOS44Yy0zMS40LDAtNjktMTcuNy02OS04OVYwaDM2LjR2MTEyLjdjMCwzOC43LDExLjYsNjQuNyw0NC42LDY0LjdjMTAuMy0wLjIsMjAuNC0zLjUsMjguOS05LjQgYzguNS01LjksMTUuMS0xNC4zLDE4LjktMjMuOWMyLjItNi4xLDMuMy0xMi41LDMuMy0xOC45VjAuMmgzNi40VjE0OEgtMzEyTC0zMTIsMTQ4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuMDEzMzIyLCA1My40Nzk2MzgpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS43MDY0NTgsIDAuMjMxNDI1KSI+CiAgICAgICAgPHBhdGggZD0iTS00NzguNiw3MS40YzAtMjYtMC44LTQ3LTEuNy02Ni43aDMyLjdsMS43LDM0LjhoMC44YzcuMS0xMi41LDE3LjUtMjIuOCwzMC4xLTI5LjcgYzEyLjUtNywyNi43LTEwLjMsNDEtOS44YzQ4LjMsMCw4NC43LDQxLjcsODQuNywxMDMuM2MwLDczLjEtNDMuNywxMDkuMi05MSwxMDkuMmMtMTIuMSwwLjUtMjQuMi0yLjItMzUtNy44IGMtMTAuOC01LjYtMTkuOS0xMy45LTI2LjYtMjQuMmgtMC44VjI5MWgtMzZ2LTIyMEwtNDc4LjYsNzEuNEwtNDc4LjYsNzEuNHogTS00NDIuNiwxMjUuNmMwLjEsNS4xLDAuNiwxMC4xLDEuNywxNS4xIGMzLDEyLjMsOS45LDIzLjMsMTkuOCwzMS4xYzkuOSw3LjgsMjIuMSwxMi4xLDM0LjcsMTIuMWMzOC41LDAsNjAuNy0zMS45LDYwLjctNzguNWMwLTQwLjctMjEuMS03NS42LTU5LjUtNzUuNiBjLTEyLjksMC40LTI1LjMsNS4xLTM1LjMsMTMuNGMtOS45LDguMy0xNi45LDE5LjctMTkuNiwzMi40Yy0xLjUsNC45LTIuMywxMC0yLjUsMTUuMVYxMjUuNkwtNDQyLjYsMTI1LjZMLTQ0Mi42LDEyNS42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MDYuNzQwNzI2LCA1Ni44MzcxMDQpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC43NTEyMjYsIDEuOTg5Mjk5KSI+CiAgICAgICAgPHBhdGggZD0iTS00NDAuOCwwbDQzLjcsMTIwLjFjNC41LDEzLjQsOS41LDI5LjQsMTIuOCw0MS43aDAuOGMzLjctMTIuMiw3LjktMjcuNywxMi44LTQyLjQgbDM5LjctMTE5LjJoMzguNUwtMzQ2LjksMTQ1Yy0yNiw2OS43LTQzLjcsMTA1LjQtNjguNiwxMjcuMmMtMTIuNSwxMS43LTI3LjksMjAtNDQuNiwyMy45bC05LjEtMzEuMSBjMTEuNy0zLjksMjIuNS0xMC4xLDMxLjgtMTguMWMxMy4yLTExLjEsMjMuNy0yNS4yLDMwLjYtNDEuMmMxLjUtMi44LDIuNS01LjcsMi45LTguOGMtMC4zLTMuMy0xLjItNi42LTIuNS05LjdMLTQ4MC4yLDAuMSBoMzkuN0wtNDQwLjgsMEwtNDQwLjgsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODIyLjc0ODEwNCwgMC4wMDAwMDApIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS40NjQwNTAsIDAuMzc4OTE0KSI+CiAgICAgICAgPHBhdGggZD0iTS00MTMuNywwdjU4LjNoNTJ2MjguMmgtNTJWMTk2YzAsMjUsNywzOS41LDI3LjMsMzkuNWM3LjEsMC4xLDE0LjItMC43LDIxLjEtMi41IGwxLjcsMjcuN2MtMTAuMywzLjctMjEuMyw1LjQtMzIuMiw1Yy03LjMsMC40LTE0LjYtMC43LTIxLjMtMy40Yy02LjgtMi43LTEyLjktNi44LTE3LjktMTIuMWMtMTAuMy0xMC45LTE0LjEtMjktMTQuMS01Mi45IFY4Ni41aC0zMVY1OC4zaDMxVjkuNkwtNDEzLjcsMEwtNDEzLjcsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTc0LjQzMzI4NiwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAuOTkwMDM0LCAwLjYxMDMzOSkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDQ1LjgsMTEzYzAuOCw1MCwzMi4yLDcwLjYsNjguNiw3MC42YzE5LDAuNiwzNy45LTMsNTUuMy0xMC41bDYuMiwyNi40IGMtMjAuOSw4LjktNDMuNSwxMy4xLTY2LjIsMTIuNmMtNjEuNSwwLTk4LjMtNDEuMi05OC4zLTEwMi41Qy00ODAuMiw0OC4yLTQ0NC43LDAtMzg2LjUsMGM2NS4yLDAsODIuNyw1OC4zLDgyLjcsOTUuNyBjLTAuMSw1LjgtMC41LDExLjUtMS4yLDE3LjJoLTE0MC42SC00NDUuOEwtNDQ1LjgsMTEzeiBNLTMzOS4yLDg2LjZjMC40LTIzLjUtOS41LTYwLjEtNTAuNC02MC4xIGMtMzYuOCwwLTUyLjgsMzQuNC01NS43LDYwLjFILTMzOS4yTC0zMzkuMiw4Ni42TC0zMzkuMiw4Ni42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAxLjk2MTA1OCwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuMTc5NjQwLCAwLjcwNTA2OCkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDc4LjYsNjhjMC0yMy45LTAuNC00NC41LTEuNy02My40aDMxLjhsMS4yLDM5LjloMS43YzkuMS0yNy4zLDMxLTQ0LjUsNTUuMy00NC41IGMzLjUtMC4xLDcsMC40LDEwLjMsMS4ydjM0LjhjLTQuMS0wLjktOC4yLTEuMy0xMi40LTEuMmMtMjUuNiwwLTQzLjcsMTkuNy00OC43LDQ3LjRjLTEsNS43LTEuNiwxMS41LTEuNywxNy4ydjEwOC4zaC0zNlY2OCBMLTQ3OC42LDY4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCBkPSJNMTM1Mi4zLDMyNi4yaDM3VjI4aC0zN1YzMjYuMnogTTE2MDQuOCwzMjYuMmMtMi41LTEzLjktMy40LTMxLjEtMy40LTQ4Ljd2LTc2IGMwLTQwLjctMTUuMS04My4xLTc3LjMtODMuMWMtMjUuNiwwLTUwLDcuMS02Ni44LDE4LjFsOC40LDI0LjRjMTQuMy05LjIsMzQtMTUuMSw1My0xNS4xYzQxLjYsMCw0Ni4yLDMwLjIsNDYuMiw0N3Y0LjIgYy03OC42LTAuNC0xMjIuMywyNi41LTEyMi4zLDc1LjZjMCwyOS40LDIxLDU4LjQsNjIuMiw1OC40YzI5LDAsNTAuOS0xNC4zLDYyLjItMzAuMmgxLjNsMi45LDI1LjZIMTYwNC44eiBNMTU2NS43LDI1Ny43IGMwLDMuOC0wLjgsOC0yLjEsMTEuOGMtNS45LDE3LjItMjIuNywzNC00OS4yLDM0Yy0xOC45LDAtMzQuOS0xMS4zLTM0LjktMzUuM2MwLTM5LjUsNDUuOC00Ni42LDg2LjItNDUuOFYyNTcuN3ogTTE2OTguNSwzMjYuMiBsMS43LTMzLjZoMS4zYzE1LjEsMjYuOSwzOC43LDM4LjIsNjguMSwzOC4yYzQ1LjQsMCw5MS4yLTM2LjEsOTEuMi0xMDguOGMwLjQtNjEuNy0zNS4zLTEwMy43LTg1LjctMTAzLjcgYy0zMi44LDAtNTYuMywxNC43LTY5LjMsMzcuNGgtMC44VjI4aC0zNi42djI0NS43YzAsMTguMS0wLjgsMzguNi0xLjcsNTIuNUgxNjk4LjV6IE0xNzA0LjgsMjA4LjJjMC01LjksMS4zLTEwLjksMi4xLTE1LjEgYzcuNi0yOC4xLDMxLjEtNDUuNCw1Ni4zLTQ1LjRjMzkuNSwwLDYwLjUsMzQuOSw2MC41LDc1LjZjMCw0Ni42LTIzLjEsNzguMS02MS44LDc4LjFjLTI2LjksMC00OC4zLTE3LjYtNTUuNS00My4zIGMtMC44LTQuMi0xLjctOC44LTEuNy0xMy40VjIwOC4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzYxNjE2MSIgZD0iTTE1IDlIOXY2aDZWOXptLTIgNGgtMnYtMmgydjJ6bTgtMlY5aC0yVjdjMC0xLjEtLjktMi0yLTJoLTJWM2gtMnYyaC0yVjNIOXYySDdjLTEuMSAwLTIgLjktMiAydjJIM3YyaDJ2MkgzdjJoMnYyYzAgMS4xLjkgMiAyIDJoMnYyaDJ2LTJoMnYyaDJ2LTJoMmMxLjEgMCAyLS45IDItMnYtMmgydi0yaC0ydi0yaDJ6bS00IDZIN1Y3aDEwdjEweiIvPgo8L3N2Zz4K);
  --jp-icon-keyboard: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMTdjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY3YzAtMS4xLS45LTItMi0yem0tOSAzaDJ2MmgtMlY4em0wIDNoMnYyaC0ydi0yek04IDhoMnYySDhWOHptMCAzaDJ2Mkg4di0yem0tMSAySDV2LTJoMnYyem0wLTNINVY4aDJ2MnptOSA3SDh2LTJoOHYyem0wLTRoLTJ2LTJoMnYyem0wLTNoLTJWOGgydjJ6bTMgM2gtMnYtMmgydjJ6bTAtM2gtMlY4aDJ2MnoiLz4KPC9zdmc+Cg==);
  --jp-icon-launch: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMzIgMzIiIHdpZHRoPSIzMiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0yNiwyOEg2YTIuMDAyNywyLjAwMjcsMCwwLDEtMi0yVjZBMi4wMDI3LDIuMDAyNywwLDAsMSw2LDRIMTZWNkg2VjI2SDI2VjE2aDJWMjZBMi4wMDI3LDIuMDAyNywwLDAsMSwyNiwyOFoiLz4KICAgIDxwb2x5Z29uIHBvaW50cz0iMjAgMiAyMCA0IDI2LjU4NiA0IDE4IDEyLjU4NiAxOS40MTQgMTQgMjggNS40MTQgMjggMTIgMzAgMTIgMzAgMiAyMCAyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-launcher: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkgMTlINVY1aDdWM0g1YTIgMiAwIDAwLTIgMnYxNGEyIDIgMCAwMDIgMmgxNGMxLjEgMCAyLS45IDItMnYtN2gtMnY3ek0xNCAzdjJoMy41OWwtOS44MyA5LjgzIDEuNDEgMS40MUwxOSA2LjQxVjEwaDJWM2gtN3oiLz4KPC9zdmc+Cg==);
  --jp-icon-line-form: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IndoaXRlIiBkPSJNNS44OCA0LjEyTDEzLjc2IDEybC03Ljg4IDcuODhMOCAyMmwxMC0xMEw4IDJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-link: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMuOSAxMmMwLTEuNzEgMS4zOS0zLjEgMy4xLTMuMWg0VjdIN2MtMi43NiAwLTUgMi4yNC01IDVzMi4yNCA1IDUgNWg0di0xLjlIN2MtMS43MSAwLTMuMS0xLjM5LTMuMS0zLjF6TTggMTNoOHYtMkg4djJ6bTktNmgtNHYxLjloNGMxLjcxIDAgMy4xIDEuMzkgMy4xIDMuMXMtMS4zOSAzLjEtMy4xIDMuMWgtNFYxN2g0YzIuNzYgMCA1LTIuMjQgNS01cy0yLjI0LTUtNS01eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xOSA1djE0SDVWNWgxNG0xLjEtMkgzLjljLS41IDAtLjkuNC0uOS45djE2LjJjMCAuNC40LjkuOS45aDE2LjJjLjQgMCAuOS0uNS45LS45VjMuOWMwLS41LS41LS45LS45LS45ek0xMSA3aDZ2MmgtNlY3em0wIDRoNnYyaC02di0yem0wIDRoNnYyaC02ek03IDdoMnYySDd6bTAgNGgydjJIN3ptMCA0aDJ2Mkg3eiIvPgo8L3N2Zz4K);
  --jp-icon-markdown: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjN0IxRkEyIiBkPSJNNSAxNC45aDEybC02LjEgNnptOS40LTYuOGMwLTEuMy0uMS0yLjktLjEtNC41LS40IDEuNC0uOSAyLjktMS4zIDQuM2wtMS4zIDQuM2gtMkw4LjUgNy45Yy0uNC0xLjMtLjctMi45LTEtNC4zLS4xIDEuNi0uMSAzLjItLjIgNC42TDcgMTIuNEg0LjhsLjctMTFoMy4zTDEwIDVjLjQgMS4yLjcgMi43IDEgMy45LjMtMS4yLjctMi42IDEtMy45bDEuMi0zLjdoMy4zbC42IDExaC0yLjRsLS4zLTQuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-move-down: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBkPSJNMTIuNDcxIDcuNTI4OTlDMTIuNzYzMiA3LjIzNjg0IDEyLjc2MzIgNi43NjMxNiAxMi40NzEgNi40NzEwMVY2LjQ3MTAxQzEyLjE3OSA2LjE3OTA1IDExLjcwNTcgNi4xNzg4NCAxMS40MTM1IDYuNDcwNTRMNy43NSAxMC4xMjc1VjEuNzVDNy43NSAxLjMzNTc5IDcuNDE0MjEgMSA3IDFWMUM2LjU4NTc5IDEgNi4yNSAxLjMzNTc5IDYuMjUgMS43NVYxMC4xMjc1TDIuNTk3MjYgNi40NjgyMkMyLjMwMzM4IDYuMTczODEgMS44MjY0MSA2LjE3MzU5IDEuNTMyMjYgNi40Njc3NFY2LjQ2Nzc0QzEuMjM4MyA2Ljc2MTcgMS4yMzgzIDcuMjM4MyAxLjUzMjI2IDcuNTMyMjZMNi4yOTI4OSAxMi4yOTI5QzYuNjgzNDIgMTIuNjgzNCA3LjMxNjU4IDEyLjY4MzQgNy43MDcxMSAxMi4yOTI5TDEyLjQ3MSA3LjUyODk5WiIgZmlsbD0iIzYxNjE2MSIvPgo8L3N2Zz4K);
  --jp-icon-move-up: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBkPSJNMS41Mjg5OSA2LjQ3MTAxQzEuMjM2ODQgNi43NjMxNiAxLjIzNjg0IDcuMjM2ODQgMS41Mjg5OSA3LjUyODk5VjcuNTI4OTlDMS44MjA5NSA3LjgyMDk1IDIuMjk0MjYgNy44MjExNiAyLjU4NjQ5IDcuNTI5NDZMNi4yNSAzLjg3MjVWMTIuMjVDNi4yNSAxMi42NjQyIDYuNTg1NzkgMTMgNyAxM1YxM0M3LjQxNDIxIDEzIDcuNzUgMTIuNjY0MiA3Ljc1IDEyLjI1VjMuODcyNUwxMS40MDI3IDcuNTMxNzhDMTEuNjk2NiA3LjgyNjE5IDEyLjE3MzYgNy44MjY0MSAxMi40Njc3IDcuNTMyMjZWNy41MzIyNkMxMi43NjE3IDcuMjM4MyAxMi43NjE3IDYuNzYxNyAxMi40Njc3IDYuNDY3NzRMNy43MDcxMSAxLjcwNzExQzcuMzE2NTggMS4zMTY1OCA2LjY4MzQyIDEuMzE2NTggNi4yOTI4OSAxLjcwNzExTDEuNTI4OTkgNi40NzEwMVoiIGZpbGw9IiM2MTYxNjEiLz4KPC9zdmc+Cg==);
  --jp-icon-new-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDZoLThsLTItMkg0Yy0xLjExIDAtMS45OS44OS0xLjk5IDJMMiAxOGMwIDEuMTEuODkgMiAyIDJoMTZjMS4xMSAwIDItLjg5IDItMlY4YzAtMS4xMS0uODktMi0yLTJ6bS0xIDhoLTN2M2gtMnYtM2gtM3YtMmgzVjloMnYzaDN2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-not-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI1IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMTkgMTcuMTg0NCAyLjk2OTY4IDE0LjMwMzIgMS44NjA5NCAxMS40NDA5WiIvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24yIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iMiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOS4zMTU5MiA5LjMyMDMxKSIgZD0iTTcuMzY4NDIgMEwwIDcuMzY0NzkiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDkuMzE1OTIgMTYuNjgzNikgc2NhbGUoMSAtMSkiIGQ9Ik03LjM2ODQyIDBMMCA3LjM2NDc5Ii8+Cjwvc3ZnPgo=);
  --jp-icon-notebook: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtbm90ZWJvb2staWNvbi1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNFRjZDMDAiPgogICAgPHBhdGggZD0iTTE4LjcgMy4zdjE1LjRIMy4zVjMuM2gxNS40bTEuNS0xLjVIMS44djE4LjNoMTguM2wuMS0xOC4zeiIvPgogICAgPHBhdGggZD0iTTE2LjUgMTYuNWwtNS40LTQuMy01LjYgNC4zdi0xMWgxMXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-numbering: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTQgMTlINlYxOS41SDVWMjAuNUg2VjIxSDRWMjJIN1YxOEg0VjE5Wk01IDEwSDZWNkg0VjdINVYxMFpNNCAxM0g1LjhMNCAxNS4xVjE2SDdWMTVINS4yTDcgMTIuOVYxMkg0VjEzWk05IDdWOUgyM1Y3SDlaTTkgMjFIMjNWMTlIOVYyMVpNOSAxNUgyM1YxM0g5VjE1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-offline-bolt: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDIuMDJjLTUuNTEgMC05Ljk4IDQuNDctOS45OCA5Ljk4czQuNDcgOS45OCA5Ljk4IDkuOTggOS45OC00LjQ3IDkuOTgtOS45OFMxNy41MSAyLjAyIDEyIDIuMDJ6TTExLjQ4IDIwdi02LjI2SDhMMTMgNHY2LjI2aDMuMzVMMTEuNDggMjB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-palette: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE4IDEzVjIwSDRWNkg5LjAyQzkuMDcgNS4yOSA5LjI0IDQuNjIgOS41IDRINEMyLjkgNCAyIDQuOSAyIDZWMjBDMiAyMS4xIDIuOSAyMiA0IDIySDE4QzE5LjEgMjIgMjAgMjEuMSAyMCAyMFYxNUwxOCAxM1pNMTkuMyA4Ljg5QzE5Ljc0IDguMTkgMjAgNy4zOCAyMCA2LjVDMjAgNC4wMSAxNy45OSAyIDE1LjUgMkMxMy4wMSAyIDExIDQuMDEgMTEgNi41QzExIDguOTkgMTMuMDEgMTEgMTUuNDkgMTFDMTYuMzcgMTEgMTcuMTkgMTAuNzQgMTcuODggMTAuM0wyMSAxMy40MkwyMi40MiAxMkwxOS4zIDguODlaTTE1LjUgOUMxNC4xMiA5IDEzIDcuODggMTMgNi41QzEzIDUuMTIgMTQuMTIgNCAxNS41IDRDMTYuODggNCAxOCA1LjEyIDE4IDYuNUMxOCA3Ljg4IDE2Ljg4IDkgMTUuNSA5WiIvPgogICAgPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00IDZIOS4wMTg5NEM5LjAwNjM5IDYuMTY1MDIgOSA2LjMzMTc2IDkgNi41QzkgOC44MTU3NyAxMC4yMTEgMTAuODQ4NyAxMi4wMzQzIDEySDlWMTRIMTZWMTIuOTgxMUMxNi41NzAzIDEyLjkzNzcgMTcuMTIgMTIuODIwNyAxNy42Mzk2IDEyLjYzOTZMMTggMTNWMjBINFY2Wk04IDhINlYxMEg4VjhaTTYgMTJIOFYxNEg2VjEyWk04IDE2SDZWMThIOFYxNlpNOSAxNkgxNlYxOEg5VjE2WiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-paste: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE5IDJoLTQuMThDMTQuNC44NCAxMy4zIDAgMTIgMGMtMS4zIDAtMi40Ljg0LTIuODIgMkg1Yy0xLjEgMC0yIC45LTIgMnYxNmMwIDEuMS45IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjRjMC0xLjEtLjktMi0yLTJ6bS03IDBjLjU1IDAgMSAuNDUgMSAxcy0uNDUgMS0xIDEtMS0uNDUtMS0xIC40NS0xIDEtMXptNyAxOEg1VjRoMnYzaDEwVjRoMnYxNnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-pdf: url(data:image/svg+xml;base64,PHN2ZwogICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyMiAyMiIgd2lkdGg9IjE2Ij4KICAgIDxwYXRoIHRyYW5zZm9ybT0icm90YXRlKDQ1KSIgY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI0ZGMkEyQSIKICAgICAgIGQ9Im0gMjIuMzQ0MzY5LC0zLjAxNjM2NDIgaCA1LjYzODYwNCB2IDEuNTc5MjQzMyBoIC0zLjU0OTIyNyB2IDEuNTA4NjkyOTkgaCAzLjMzNzU3NiBWIDEuNjUwODE1NCBoIC0zLjMzNzU3NiB2IDMuNDM1MjYxMyBoIC0yLjA4OTM3NyB6IG0gLTcuMTM2NDQ0LDEuNTc5MjQzMyB2IDQuOTQzOTU0MyBoIDAuNzQ4OTIgcSAxLjI4MDc2MSwwIDEuOTUzNzAzLC0wLjYzNDk1MzUgMC42NzgzNjksLTAuNjM0OTUzNSAwLjY3ODM2OSwtMS44NDUxNjQxIDAsLTEuMjA0NzgzNTUgLTAuNjcyOTQyLC0xLjgzNDMxMDExIC0wLjY3Mjk0MiwtMC42Mjk1MjY1OSAtMS45NTkxMywtMC42Mjk1MjY1OSB6IG0gLTIuMDg5Mzc3LC0xLjU3OTI0MzMgaCAyLjIwMzM0MyBxIDEuODQ1MTY0LDAgMi43NDYwMzksMC4yNjU5MjA3IDAuOTA2MzAxLDAuMjYwNDkzNyAxLjU1MjEwOCwwLjg5MDAyMDMgMC41Njk4MywwLjU0ODEyMjMgMC44NDY2MDUsMS4yNjQ0ODAwNiAwLjI3Njc3NCwwLjcxNjM1NzgxIDAuMjc2Nzc0LDEuNjIyNjU4OTQgMCwwLjkxNzE1NTEgLTAuMjc2Nzc0LDEuNjM4OTM5OSAtMC4yNzY3NzUsMC43MTYzNTc4IC0wLjg0NjYwNSwxLjI2NDQ4IC0wLjY1MTIzNCwwLjYyOTUyNjYgLTEuNTYyOTYyLDAuODk1NDQ3MyAtMC45MTE3MjgsMC4yNjA0OTM3IC0yLjczNTE4NSwwLjI2MDQ5MzcgaCAtMi4yMDMzNDMgeiBtIC04LjE0NTg1NjUsMCBoIDMuNDY3ODIzIHEgMS41NDY2ODE2LDAgMi4zNzE1Nzg1LDAuNjg5MjIzIDAuODMwMzI0LDAuNjgzNzk2MSAwLjgzMDMyNCwxLjk1MzcwMzE0IDAsMS4yNzUzMzM5NyAtMC44MzAzMjQsMS45NjQ1NTcwNiBRIDkuOTg3MTk2MSwyLjI3NDkxNSA4LjQ0MDUxNDUsMi4yNzQ5MTUgSCA3LjA2MjA2ODQgViA1LjA4NjA3NjcgSCA0Ljk3MjY5MTUgWiBtIDIuMDg5Mzc2OSwxLjUxNDExOTkgdiAyLjI2MzAzOTQzIGggMS4xNTU5NDEgcSAwLjYwNzgxODgsMCAwLjkzODg2MjksLTAuMjkzMDU1NDcgMC4zMzEwNDQxLC0wLjI5ODQ4MjQxIDAuMzMxMDQ0MSwtMC44NDExNzc3MiAwLC0wLjU0MjY5NTMxIC0wLjMzMTA0NDEsLTAuODM1NzUwNzQgLTAuMzMxMDQ0MSwtMC4yOTMwNTU1IC0wLjkzODg2MjksLTAuMjkzMDU1NSB6IgovPgo8L3N2Zz4K);
  --jp-icon-python: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iLTEwIC0xMCAxMzEuMTYxMzYxNjk0MzM1OTQgMTMyLjM4ODk5OTkzODk2NDg0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMzA2OTk4IiBkPSJNIDU0LjkxODc4NSw5LjE5Mjc0MjFlLTQgQyA1MC4zMzUxMzIsMC4wMjIyMTcyNyA0NS45NTc4NDYsMC40MTMxMzY5NyA0Mi4xMDYyODUsMS4wOTQ2NjkzIDMwLjc2MDA2OSwzLjA5OTE3MzEgMjguNzAwMDM2LDcuMjk0NzcxNCAyOC43MDAwMzUsMTUuMDMyMTY5IHYgMTAuMjE4NzUgaCAyNi44MTI1IHYgMy40MDYyNSBoIC0yNi44MTI1IC0xMC4wNjI1IGMgLTcuNzkyNDU5LDAgLTE0LjYxNTc1ODgsNC42ODM3MTcgLTE2Ljc0OTk5OTgsMTMuNTkzNzUgLTIuNDYxODE5OTgsMTAuMjEyOTY2IC0yLjU3MTAxNTA4LDE2LjU4NjAyMyAwLDI3LjI1IDEuOTA1OTI4Myw3LjkzNzg1MiA2LjQ1NzU0MzIsMTMuNTkzNzQ4IDE0LjI0OTk5OTgsMTMuNTkzNzUgaCA5LjIxODc1IHYgLTEyLjI1IGMgMCwtOC44NDk5MDIgNy42NTcxNDQsLTE2LjY1NjI0OCAxNi43NSwtMTYuNjU2MjUgaCAyNi43ODEyNSBjIDcuNDU0OTUxLDAgMTMuNDA2MjUzLC02LjEzODE2NCAxMy40MDYyNSwtMTMuNjI1IHYgLTI1LjUzMTI1IGMgMCwtNy4yNjYzMzg2IC02LjEyOTk4LC0xMi43MjQ3NzcxIC0xMy40MDYyNSwtMTMuOTM3NDk5NyBDIDY0LjI4MTU0OCwwLjMyNzk0Mzk3IDU5LjUwMjQzOCwtMC4wMjAzNzkwMyA1NC45MTg3ODUsOS4xOTI3NDIxZS00IFogbSAtMTQuNSw4LjIxODc1MDEyNTc5IGMgMi43Njk1NDcsMCA1LjAzMTI1LDIuMjk4NjQ1NiA1LjAzMTI1LDUuMTI0OTk5NiAtMmUtNiwyLjgxNjMzNiAtMi4yNjE3MDMsNS4wOTM3NSAtNS4wMzEyNSw1LjA5Mzc1IC0yLjc3OTQ3NiwtMWUtNiAtNS4wMzEyNSwtMi4yNzc0MTUgLTUuMDMxMjUsLTUuMDkzNzUgLTEwZS03LC0yLjgyNjM1MyAyLjI1MTc3NCwtNS4xMjQ5OTk2IDUuMDMxMjUsLTUuMTI0OTk5NiB6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2ZmZDQzYiIgZD0ibSA4NS42Mzc1MzUsMjguNjU3MTY5IHYgMTEuOTA2MjUgYyAwLDkuMjMwNzU1IC03LjgyNTg5NSwxNi45OTk5OTkgLTE2Ljc1LDE3IGggLTI2Ljc4MTI1IGMgLTcuMzM1ODMzLDAgLTEzLjQwNjI0OSw2LjI3ODQ4MyAtMTMuNDA2MjUsMTMuNjI1IHYgMjUuNTMxMjQ3IGMgMCw3LjI2NjM0NCA2LjMxODU4OCwxMS41NDAzMjQgMTMuNDA2MjUsMTMuNjI1MDA0IDguNDg3MzMxLDIuNDk1NjEgMTYuNjI2MjM3LDIuOTQ2NjMgMjYuNzgxMjUsMCA2Ljc1MDE1NSwtMS45NTQzOSAxMy40MDYyNTMsLTUuODg3NjEgMTMuNDA2MjUsLTEzLjYyNTAwNCBWIDg2LjUwMDkxOSBoIC0yNi43ODEyNSB2IC0zLjQwNjI1IGggMjYuNzgxMjUgMTMuNDA2MjU0IGMgNy43OTI0NjEsMCAxMC42OTYyNTEsLTUuNDM1NDA4IDEzLjQwNjI0MSwtMTMuNTkzNzUgMi43OTkzMywtOC4zOTg4ODYgMi42ODAyMiwtMTYuNDc1Nzc2IDAsLTI3LjI1IC0xLjkyNTc4LC03Ljc1NzQ0MSAtNS42MDM4NywtMTMuNTkzNzUgLTEzLjQwNjI0MSwtMTMuNTkzNzUgeiBtIC0xNS4wNjI1LDY0LjY1NjI1IGMgMi43Nzk0NzgsM2UtNiA1LjAzMTI1LDIuMjc3NDE3IDUuMDMxMjUsNS4wOTM3NDcgLTJlLTYsMi44MjYzNTQgLTIuMjUxNzc1LDUuMTI1MDA0IC01LjAzMTI1LDUuMTI1MDA0IC0yLjc2OTU1LDAgLTUuMDMxMjUsLTIuMjk4NjUgLTUuMDMxMjUsLTUuMTI1MDA0IDJlLTYsLTIuODE2MzMgMi4yNjE2OTcsLTUuMDkzNzQ3IDUuMDMxMjUsLTUuMDkzNzQ3IHoiLz4KPC9zdmc+Cg==);
  --jp-icon-r-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjE5NkYzIiBkPSJNNC40IDIuNWMxLjItLjEgMi45LS4zIDQuOS0uMyAyLjUgMCA0LjEuNCA1LjIgMS4zIDEgLjcgMS41IDEuOSAxLjUgMy41IDAgMi0xLjQgMy41LTIuOSA0LjEgMS4yLjQgMS43IDEuNiAyLjIgMyAuNiAxLjkgMSAzLjkgMS4zIDQuNmgtMy44Yy0uMy0uNC0uOC0xLjctMS4yLTMuN3MtMS4yLTIuNi0yLjYtMi42aC0uOXY2LjRINC40VjIuNXptMy43IDYuOWgxLjRjMS45IDAgMi45LS45IDIuOS0yLjNzLTEtMi4zLTIuOC0yLjNjLS43IDAtMS4zIDAtMS42LjJ2NC41aC4xdi0uMXoiLz4KPC9zdmc+Cg==);
  --jp-icon-react: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMTUwIDE1MCA1NDEuOSAyOTUuMyI+CiAgPGcgY2xhc3M9ImpwLWljb24tYnJhbmQyIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxREFGQiI+CiAgICA8cGF0aCBkPSJNNjY2LjMgMjk2LjVjMC0zMi41LTQwLjctNjMuMy0xMDMuMS04Mi40IDE0LjQtNjMuNiA4LTExNC4yLTIwLjItMTMwLjQtNi41LTMuOC0xNC4xLTUuNi0yMi40LTUuNnYyMi4zYzQuNiAwIDguMy45IDExLjQgMi42IDEzLjYgNy44IDE5LjUgMzcuNSAxNC45IDc1LjctMS4xIDkuNC0yLjkgMTkuMy01LjEgMjkuNC0xOS42LTQuOC00MS04LjUtNjMuNS0xMC45LTEzLjUtMTguNS0yNy41LTM1LjMtNDEuNi01MCAzMi42LTMwLjMgNjMuMi00Ni45IDg0LTQ2LjlWNzhjLTI3LjUgMC02My41IDE5LjYtOTkuOSA1My42LTM2LjQtMzMuOC03Mi40LTUzLjItOTkuOS01My4ydjIyLjNjMjAuNyAwIDUxLjQgMTYuNSA4NCA0Ni42LTE0IDE0LjctMjggMzEuNC00MS4zIDQ5LjktMjIuNiAyLjQtNDQgNi4xLTYzLjYgMTEtMi4zLTEwLTQtMTkuNy01LjItMjktNC43LTM4LjIgMS4xLTY3LjkgMTQuNi03NS44IDMtMS44IDYuOS0yLjYgMTEuNS0yLjZWNzguNWMtOC40IDAtMTYgMS44LTIyLjYgNS42LTI4LjEgMTYuMi0zNC40IDY2LjctMTkuOSAxMzAuMS02Mi4yIDE5LjItMTAyLjcgNDkuOS0xMDIuNyA4Mi4zIDAgMzIuNSA0MC43IDYzLjMgMTAzLjEgODIuNC0xNC40IDYzLjYtOCAxMTQuMiAyMC4yIDEzMC40IDYuNSAzLjggMTQuMSA1LjYgMjIuNSA1LjYgMjcuNSAwIDYzLjUtMTkuNiA5OS45LTUzLjYgMzYuNCAzMy44IDcyLjQgNTMuMiA5OS45IDUzLjIgOC40IDAgMTYtMS44IDIyLjYtNS42IDI4LjEtMTYuMiAzNC40LTY2LjcgMTkuOS0xMzAuMSA2Mi0xOS4xIDEwMi41LTQ5LjkgMTAyLjUtODIuM3ptLTEzMC4yLTY2LjdjLTMuNyAxMi45LTguMyAyNi4yLTEzLjUgMzkuNS00LjEtOC04LjQtMTYtMTMuMS0yNC00LjYtOC05LjUtMTUuOC0xNC40LTIzLjQgMTQuMiAyLjEgMjcuOSA0LjcgNDEgNy45em0tNDUuOCAxMDYuNWMtNy44IDEzLjUtMTUuOCAyNi4zLTI0LjEgMzguMi0xNC45IDEuMy0zMCAyLTQ1LjIgMi0xNS4xIDAtMzAuMi0uNy00NS0xLjktOC4zLTExLjktMTYuNC0yNC42LTI0LjItMzgtNy42LTEzLjEtMTQuNS0yNi40LTIwLjgtMzkuOCA2LjItMTMuNCAxMy4yLTI2LjggMjAuNy0zOS45IDcuOC0xMy41IDE1LjgtMjYuMyAyNC4xLTM4LjIgMTQuOS0xLjMgMzAtMiA0NS4yLTIgMTUuMSAwIDMwLjIuNyA0NSAxLjkgOC4zIDExLjkgMTYuNCAyNC42IDI0LjIgMzggNy42IDEzLjEgMTQuNSAyNi40IDIwLjggMzkuOC02LjMgMTMuNC0xMy4yIDI2LjgtMjAuNyAzOS45em0zMi4zLTEzYzUuNCAxMy40IDEwIDI2LjggMTMuOCAzOS44LTEzLjEgMy4yLTI2LjkgNS45LTQxLjIgOCA0LjktNy43IDkuOC0xNS42IDE0LjQtMjMuNyA0LjYtOCA4LjktMTYuMSAxMy0yNC4xek00MjEuMiA0MzBjLTkuMy05LjYtMTguNi0yMC4zLTI3LjgtMzIgOSAuNCAxOC4yLjcgMjcuNS43IDkuNCAwIDE4LjctLjIgMjcuOC0uNy05IDExLjctMTguMyAyMi40LTI3LjUgMzJ6bS03NC40LTU4LjljLTE0LjItMi4xLTI3LjktNC43LTQxLTcuOSAzLjctMTIuOSA4LjMtMjYuMiAxMy41LTM5LjUgNC4xIDggOC40IDE2IDEzLjEgMjQgNC43IDggOS41IDE1LjggMTQuNCAyMy40ek00MjAuNyAxNjNjOS4zIDkuNiAxOC42IDIwLjMgMjcuOCAzMi05LS40LTE4LjItLjctMjcuNS0uNy05LjQgMC0xOC43LjItMjcuOC43IDktMTEuNyAxOC4zLTIyLjQgMjcuNS0zMnptLTc0IDU4LjljLTQuOSA3LjctOS44IDE1LjYtMTQuNCAyMy43LTQuNiA4LTguOSAxNi0xMyAyNC01LjQtMTMuNC0xMC0yNi44LTEzLjgtMzkuOCAxMy4xLTMuMSAyNi45LTUuOCA0MS4yLTcuOXptLTkwLjUgMTI1LjJjLTM1LjQtMTUuMS01OC4zLTM0LjktNTguMy01MC42IDAtMTUuNyAyMi45LTM1LjYgNTguMy01MC42IDguNi0zLjcgMTgtNyAyNy43LTEwLjEgNS43IDE5LjYgMTMuMiA0MCAyMi41IDYwLjktOS4yIDIwLjgtMTYuNiA0MS4xLTIyLjIgNjAuNi05LjktMy4xLTE5LjMtNi41LTI4LTEwLjJ6TTMxMCA0OTBjLTEzLjYtNy44LTE5LjUtMzcuNS0xNC45LTc1LjcgMS4xLTkuNCAyLjktMTkuMyA1LjEtMjkuNCAxOS42IDQuOCA0MSA4LjUgNjMuNSAxMC45IDEzLjUgMTguNSAyNy41IDM1LjMgNDEuNiA1MC0zMi42IDMwLjMtNjMuMiA0Ni45LTg0IDQ2LjktNC41LS4xLTguMy0xLTExLjMtMi43em0yMzcuMi03Ni4yYzQuNyAzOC4yLTEuMSA2Ny45LTE0LjYgNzUuOC0zIDEuOC02LjkgMi42LTExLjUgMi42LTIwLjcgMC01MS40LTE2LjUtODQtNDYuNiAxNC0xNC43IDI4LTMxLjQgNDEuMy00OS45IDIyLjYtMi40IDQ0LTYuMSA2My42LTExIDIuMyAxMC4xIDQuMSAxOS44IDUuMiAyOS4xem0zOC41LTY2LjdjLTguNiAzLjctMTggNy0yNy43IDEwLjEtNS43LTE5LjYtMTMuMi00MC0yMi41LTYwLjkgOS4yLTIwLjggMTYuNi00MS4xIDIyLjItNjAuNiA5LjkgMy4xIDE5LjMgNi41IDI4LjEgMTAuMiAzNS40IDE1LjEgNTguMyAzNC45IDU4LjMgNTAuNi0uMSAxNS43LTIzIDM1LjYtNTguNCA1MC42ek0zMjAuOCA3OC40eiIvPgogICAgPGNpcmNsZSBjeD0iNDIwLjkiIGN5PSIyOTYuNSIgcj0iNDUuNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-redo: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCBkPSJNMCAwaDI0djI0SDB6IiBmaWxsPSJub25lIi8+PHBhdGggZD0iTTE4LjQgMTAuNkMxNi41NSA4Ljk5IDE0LjE1IDggMTEuNSA4Yy00LjY1IDAtOC41OCAzLjAzLTkuOTYgNy4yMkwzLjkgMTZjMS4wNS0zLjE5IDQuMDUtNS41IDcuNi01LjUgMS45NSAwIDMuNzMuNzIgNS4xMiAxLjg4TDEzIDE2aDlWN2wtMy42IDMuNnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-refresh: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTkgMTMuNWMtMi40OSAwLTQuNS0yLjAxLTQuNS00LjVTNi41MSA0LjUgOSA0LjVjMS4yNCAwIDIuMzYuNTIgMy4xNyAxLjMzTDEwIDhoNVYzbC0xLjc2IDEuNzZDMTIuMTUgMy42OCAxMC42NiAzIDkgMyA1LjY5IDMgMy4wMSA1LjY5IDMuMDEgOVM1LjY5IDE1IDkgMTVjMi45NyAwIDUuNDMtMi4xNiA1LjktNWgtMS41MmMtLjQ2IDItMi4yNCAzLjUtNC4zOCAzLjV6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-regex: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiBmaWxsPSIjRkZGIj4KICAgIDxjaXJjbGUgY2xhc3M9InN0MiIgY3g9IjUuNSIgY3k9IjE0LjUiIHI9IjEuNSIvPgogICAgPHJlY3QgeD0iMTIiIHk9IjQiIGNsYXNzPSJzdDIiIHdpZHRoPSIxIiBoZWlnaHQ9IjgiLz4KICAgIDxyZWN0IHg9IjguNSIgeT0iNy41IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjg2NiAtMC41IDAuNSAwLjg2NiAtMi4zMjU1IDcuMzIxOSkiIGNsYXNzPSJzdDIiIHdpZHRoPSI4IiBoZWlnaHQ9IjEiLz4KICAgIDxyZWN0IHg9IjEyIiB5PSI0IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjUgLTAuODY2IDAuODY2IDAuNSAtMC42Nzc5IDE0LjgyNTIpIiBjbGFzcz0ic3QyIiB3aWR0aD0iMSIgaGVpZ2h0PSI4Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-run: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTggNXYxNGwxMS03eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-running: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMjU2IDhDMTE5IDggOCAxMTkgOCAyNTZzMTExIDI0OCAyNDggMjQ4IDI0OC0xMTEgMjQ4LTI0OFMzOTMgOCAyNTYgOHptOTYgMzI4YzAgOC44LTcuMiAxNi0xNiAxNkgxNzZjLTguOCAwLTE2LTcuMi0xNi0xNlYxNzZjMC04LjggNy4yLTE2IDE2LTE2aDE2MGM4LjggMCAxNiA3LjIgMTYgMTZ2MTYweiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-save: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE3IDNINWMtMS4xMSAwLTIgLjktMiAydjE0YzAgMS4xLjg5IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjdsLTQtNHptLTUgMTZjLTEuNjYgMC0zLTEuMzQtMy0zczEuMzQtMyAzLTMgMyAxLjM0IDMgMy0xLjM0IDMtMyAzem0zLTEwSDVWNWgxMHY0eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-search: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-settings: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuNDMgMTIuOThjLjA0LS4zMi4wNy0uNjQuMDctLjk4cy0uMDMtLjY2LS4wNy0uOThsMi4xMS0xLjY1Yy4xOS0uMTUuMjQtLjQyLjEyLS42NGwtMi0zLjQ2Yy0uMTItLjIyLS4zOS0uMy0uNjEtLjIybC0yLjQ5IDFjLS41Mi0uNC0xLjA4LS43My0xLjY5LS45OGwtLjM4LTIuNjVBLjQ4OC40ODggMCAwMDE0IDJoLTRjLS4yNSAwLS40Ni4xOC0uNDkuNDJsLS4zOCAyLjY1Yy0uNjEuMjUtMS4xNy41OS0xLjY5Ljk4bC0yLjQ5LTFjLS4yMy0uMDktLjQ5IDAtLjYxLjIybC0yIDMuNDZjLS4xMy4yMi0uMDcuNDkuMTIuNjRsMi4xMSAxLjY1Yy0uMDQuMzItLjA3LjY1LS4wNy45OHMuMDMuNjYuMDcuOThsLTIuMTEgMS42NWMtLjE5LjE1LS4yNC40Mi0uMTIuNjRsMiAzLjQ2Yy4xMi4yMi4zOS4zLjYxLjIybDIuNDktMWMuNTIuNCAxLjA4LjczIDEuNjkuOThsLjM4IDIuNjVjLjAzLjI0LjI0LjQyLjQ5LjQyaDRjLjI1IDAgLjQ2LS4xOC40OS0uNDJsLjM4LTIuNjVjLjYxLS4yNSAxLjE3LS41OSAxLjY5LS45OGwyLjQ5IDFjLjIzLjA5LjQ5IDAgLjYxLS4yMmwyLTMuNDZjLjEyLS4yMi4wNy0uNDktLjEyLS42NGwtMi4xMS0xLjY1ek0xMiAxNS41Yy0xLjkzIDAtMy41LTEuNTctMy41LTMuNXMxLjU3LTMuNSAzLjUtMy41IDMuNSAxLjU3IDMuNSAzLjUtMS41NyAzLjUtMy41IDMuNXoiLz4KPC9zdmc+Cg==);
  --jp-icon-share: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTSAxOCAyIEMgMTYuMzU0OTkgMiAxNSAzLjM1NDk5MDQgMTUgNSBDIDE1IDUuMTkwOTUyOSAxNS4wMjE3OTEgNS4zNzcxMjI0IDE1LjA1NjY0MSA1LjU1ODU5MzggTCA3LjkyMTg3NSA5LjcyMDcwMzEgQyA3LjM5ODUzOTkgOS4yNzc4NTM5IDYuNzMyMDc3MSA5IDYgOSBDIDQuMzU0OTkwNCA5IDMgMTAuMzU0OTkgMyAxMiBDIDMgMTMuNjQ1MDEgNC4zNTQ5OTA0IDE1IDYgMTUgQyA2LjczMjA3NzEgMTUgNy4zOTg1Mzk5IDE0LjcyMjE0NiA3LjkyMTg3NSAxNC4yNzkyOTcgTCAxNS4wNTY2NDEgMTguNDM5NDUzIEMgMTUuMDIxNTU1IDE4LjYyMTUxNCAxNSAxOC44MDgzODYgMTUgMTkgQyAxNSAyMC42NDUwMSAxNi4zNTQ5OSAyMiAxOCAyMiBDIDE5LjY0NTAxIDIyIDIxIDIwLjY0NTAxIDIxIDE5IEMgMjEgMTcuMzU0OTkgMTkuNjQ1MDEgMTYgMTggMTYgQyAxNy4yNjc0OCAxNiAxNi42MDE1OTMgMTYuMjc5MzI4IDE2LjA3ODEyNSAxNi43MjI2NTYgTCA4Ljk0MzM1OTQgMTIuNTU4NTk0IEMgOC45NzgyMDk1IDEyLjM3NzEyMiA5IDEyLjE5MDk1MyA5IDEyIEMgOSAxMS44MDkwNDcgOC45NzgyMDk1IDExLjYyMjg3OCA4Ljk0MzM1OTQgMTEuNDQxNDA2IEwgMTYuMDc4MTI1IDcuMjc5Mjk2OSBDIDE2LjYwMTQ2IDcuNzIyMTQ2MSAxNy4yNjc5MjMgOCAxOCA4IEMgMTkuNjQ1MDEgOCAyMSA2LjY0NTAwOTYgMjEgNSBDIDIxIDMuMzU0OTkwNCAxOS42NDUwMSAyIDE4IDIgeiBNIDE4IDQgQyAxOC41NjQxMjkgNCAxOSA0LjQzNTg3MDYgMTkgNSBDIDE5IDUuNTY0MTI5NCAxOC41NjQxMjkgNiAxOCA2IEMgMTcuNDM1ODcxIDYgMTcgNS41NjQxMjk0IDE3IDUgQyAxNyA0LjQzNTg3MDYgMTcuNDM1ODcxIDQgMTggNCB6IE0gNiAxMSBDIDYuNTY0MTI5NCAxMSA3IDExLjQzNTg3MSA3IDEyIEMgNyAxMi41NjQxMjkgNi41NjQxMjk0IDEzIDYgMTMgQyA1LjQzNTg3MDYgMTMgNSAxMi41NjQxMjkgNSAxMiBDIDUgMTEuNDM1ODcxIDUuNDM1ODcwNiAxMSA2IDExIHogTSAxOCAxOCBDIDE4LjU2NDEyOSAxOCAxOSAxOC40MzU4NzEgMTkgMTkgQyAxOSAxOS41NjQxMjkgMTguNTY0MTI5IDIwIDE4IDIwIEMgMTcuNDM1ODcxIDIwIDE3IDE5LjU2NDEyOSAxNyAxOSBDIDE3IDE4LjQzNTg3MSAxNy40MzU4NzEgMTggMTggMTggeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-spreadsheet: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNENBRjUwIiBkPSJNMi4yIDIuMnYxNy42aDE3LjZWMi4ySDIuMnptMTUuNCA3LjdoLTUuNVY0LjRoNS41djUuNXpNOS45IDQuNHY1LjVINC40VjQuNGg1LjV6bS01LjUgNy43aDUuNXY1LjVINC40di01LjV6bTcuNyA1LjV2LTUuNWg1LjV2NS41aC01LjV6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-stop: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik02IDZoMTJ2MTJINnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tab: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIxIDNIM2MtMS4xIDAtMiAuOS0yIDJ2MTRjMCAxLjEuOSAyIDIgMmgxOGMxLjEgMCAyLS45IDItMlY1YzAtMS4xLS45LTItMi0yem0wIDE2SDNWNWgxMHY0aDh2MTB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-table-rows: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMSw4SDNWNGgxOFY4eiBNMjEsMTBIM3Y0aDE4VjEweiBNMjEsMTZIM3Y0aDE4VjE2eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-tag: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjgiIGhlaWdodD0iMjgiIHZpZXdCb3g9IjAgMCA0MyAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTI4LjgzMzIgMTIuMzM0TDMyLjk5OTggMTYuNTAwN0wzNy4xNjY1IDEyLjMzNEgyOC44MzMyWiIvPgoJCTxwYXRoIGQ9Ik0xNi4yMDk1IDIxLjYxMDRDMTUuNjg3MyAyMi4xMjk5IDE0Ljg0NDMgMjIuMTI5OSAxNC4zMjQ4IDIxLjYxMDRMNi45ODI5IDE0LjcyNDVDNi41NzI0IDE0LjMzOTQgNi4wODMxMyAxMy42MDk4IDYuMDQ3ODYgMTMuMDQ4MkM1Ljk1MzQ3IDExLjUyODggNi4wMjAwMiA4LjYxOTQ0IDYuMDY2MjEgNy4wNzY5NUM2LjA4MjgxIDYuNTE0NzcgNi41NTU0OCA2LjA0MzQ3IDcuMTE4MDQgNi4wMzA1NUM5LjA4ODYzIDUuOTg0NzMgMTMuMjYzOCA1LjkzNTc5IDEzLjY1MTggNi4zMjQyNUwyMS43MzY5IDEzLjYzOUMyMi4yNTYgMTQuMTU4NSAyMS43ODUxIDE1LjQ3MjQgMjEuMjYyIDE1Ljk5NDZMMTYuMjA5NSAyMS42MTA0Wk05Ljc3NTg1IDguMjY1QzkuMzM1NTEgNy44MjU2NiA4LjYyMzUxIDcuODI1NjYgOC4xODI4IDguMjY1QzcuNzQzNDYgOC43MDU3MSA3Ljc0MzQ2IDkuNDE3MzMgOC4xODI4IDkuODU2NjdDOC42MjM4MiAxMC4yOTY0IDkuMzM1ODIgMTAuMjk2NCA5Ljc3NTg1IDkuODU2NjdDMTAuMjE1NiA5LjQxNzMzIDEwLjIxNTYgOC43MDUzMyA5Ljc3NTg1IDguMjY1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-terminal: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0IiA+CiAgICA8cmVjdCBjbGFzcz0ianAtdGVybWluYWwtaWNvbi1iYWNrZ3JvdW5kLWNvbG9yIGpwLWljb24tc2VsZWN0YWJsZSIgd2lkdGg9IjIwIiBoZWlnaHQ9IjIwIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgyIDIpIiBmaWxsPSIjMzMzMzMzIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtdGVybWluYWwtaWNvbi1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUtaW52ZXJzZSIgZD0iTTUuMDU2NjQgOC43NjE3MkM1LjA1NjY0IDguNTk3NjYgNS4wMzEyNSA4LjQ1MzEyIDQuOTgwNDcgOC4zMjgxMkM0LjkzMzU5IDguMTk5MjIgNC44NTU0NyA4LjA4MjAzIDQuNzQ2MDkgNy45NzY1NkM0LjY0MDYyIDcuODcxMDkgNC41IDcuNzc1MzkgNC4zMjQyMiA3LjY4OTQ1QzQuMTUyMzQgNy41OTk2MSAzLjk0MzM2IDcuNTExNzIgMy42OTcyNyA3LjQyNTc4QzMuMzAyNzMgNy4yODUxNiAyLjk0MzM2IDcuMTM2NzIgMi42MTkxNCA2Ljk4MDQ3QzIuMjk0OTIgNi44MjQyMiAyLjAxNzU4IDYuNjQyNTggMS43ODcxMSA2LjQzNTU1QzEuNTYwNTUgNi4yMjg1MiAxLjM4NDc3IDUuOTg4MjggMS4yNTk3NyA1LjcxNDg0QzEuMTM0NzcgNS40Mzc1IDEuMDcyMjcgNS4xMDkzOCAxLjA3MjI3IDQuNzMwNDdDMS4wNzIyNyA0LjM5ODQ0IDEuMTI4OTEgNC4wOTU3IDEuMjQyMTkgMy44MjIyN0MxLjM1NTQ3IDMuNTQ0OTIgMS41MTU2MiAzLjMwNDY5IDEuNzIyNjYgMy4xMDE1NkMxLjkyOTY5IDIuODk4NDQgMi4xNzk2OSAyLjczNDM3IDIuNDcyNjYgMi42MDkzOEMyLjc2NTYyIDIuNDg0MzggMy4wOTE4IDIuNDA0MyAzLjQ1MTE3IDIuMzY5MTRWMS4xMDkzOEg0LjM4ODY3VjIuMzgwODZDNC43NDAyMyAyLjQyNzczIDUuMDU2NjQgMi41MjM0NCA1LjMzNzg5IDIuNjY3OTdDNS42MTkxNCAyLjgxMjUgNS44NTc0MiAzLjAwMTk1IDYuMDUyNzMgMy4yMzYzM0M2LjI1MTk1IDMuNDY2OCA2LjQwNDMgMy43NDAyMyA2LjUwOTc3IDQuMDU2NjRDNi42MTkxNCA0LjM2OTE0IDYuNjczODMgNC43MjA3IDYuNjczODMgNS4xMTEzM0g1LjA0NDkyQzUuMDQ0OTIgNC42Mzg2NyA0LjkzNzUgNC4yODEyNSA0LjcyMjY2IDQuMDM5MDZDNC41MDc4MSAzLjc5Mjk3IDQuMjE2OCAzLjY2OTkyIDMuODQ5NjEgMy42Njk5MkMzLjY1MDM5IDMuNjY5OTIgMy40NzY1NiAzLjY5NzI3IDMuMzI4MTIgMy43NTE5NUMzLjE4MzU5IDMuODAyNzMgMy4wNjQ0NSAzLjg3Njk1IDIuOTcwNyAzLjk3NDYxQzIuODc2OTUgNC4wNjgzNiAyLjgwNjY0IDQuMTc5NjkgMi43NTk3NyA0LjMwODU5QzIuNzE2OCA0LjQzNzUgMi42OTUzMSA0LjU3ODEyIDIuNjk1MzEgNC43MzA0N0MyLjY5NTMxIDQuODgyODEgMi43MTY4IDUuMDE5NTMgMi43NTk3NyA1LjE0MDYyQzIuODA2NjQgNS4yNTc4MSAyLjg4MjgxIDUuMzY3MTkgMi45ODgyOCA1LjQ2ODc1QzMuMDk3NjYgNS41NzAzMSAzLjI0MDIzIDUuNjY3OTcgMy40MTYwMiA1Ljc2MTcyQzMuNTkxOCA1Ljg1MTU2IDMuODEwNTUgNS45NDMzNiA0LjA3MjI3IDYuMDM3MTFDNC40NjY4IDYuMTg1NTUgNC44MjQyMiA2LjMzOTg0IDUuMTQ0NTMgNi41QzUuNDY0ODQgNi42NTYyNSA1LjczODI4IDYuODM5ODQgNS45NjQ4NCA3LjA1MDc4QzYuMTk1MzEgNy4yNTc4MSA2LjM3MTA5IDcuNSA2LjQ5MjE5IDcuNzc3MzRDNi42MTcxOSA4LjA1MDc4IDYuNjc5NjkgOC4zNzUgNi42Nzk2OSA4Ljc1QzYuNjc5NjkgOS4wOTM3NSA2LjYyMzA1IDkuNDA0MyA2LjUwOTc3IDkuNjgxNjRDNi4zOTY0OCA5Ljk1NTA4IDYuMjM0MzggMTAuMTkxNCA2LjAyMzQ0IDEwLjM5MDZDNS44MTI1IDEwLjU4OTggNS41NTg1OSAxMC43NSA1LjI2MTcyIDEwLjg3MTFDNC45NjQ4NCAxMC45ODgzIDQuNjMyODEgMTEuMDY0NSA0LjI2NTYyIDExLjA5OTZWMTIuMjQ4SDMuMzMzOThWMTEuMDk5NkMzLjAwMTk1IDExLjA2ODQgMi42Nzk2OSAxMC45OTYxIDIuMzY3MTkgMTAuODgyOEMyLjA1NDY5IDEwLjc2NTYgMS43NzczNCAxMC41OTc3IDEuNTM1MTYgMTAuMzc4OUMxLjI5Njg4IDEwLjE2MDIgMS4xMDU0NyA5Ljg4NDc3IDAuOTYwOTM4IDkuNTUyNzNDMC44MTY0MDYgOS4yMTY4IDAuNzQ0MTQxIDguODE0NDUgMC43NDQxNDEgOC4zNDU3SDIuMzc4OTFDMi4zNzg5MSA4LjYyNjk1IDIuNDE5OTIgOC44NjMyOCAyLjUwMTk1IDkuMDU0NjlDMi41ODM5OCA5LjI0MjE5IDIuNjg5NDUgOS4zOTI1OCAyLjgxODM2IDkuNTA1ODZDMi45NTExNyA5LjYxNTIzIDMuMTAxNTYgOS42OTMzNiAzLjI2OTUzIDkuNzQwMjNDMy40Mzc1IDkuNzg3MTEgMy42MDkzOCA5LjgxMDU1IDMuNzg1MTYgOS44MTA1NUM0LjIwMzEyIDkuODEwNTUgNC41MTk1MyA5LjcxMjg5IDQuNzM0MzggOS41MTc1OEM0Ljk0OTIyIDkuMzIyMjcgNS4wNTY2NCA5LjA3MDMxIDUuMDU2NjQgOC43NjE3MlpNMTMuNDE4IDEyLjI3MTVIOC4wNzQyMlYxMUgxMy40MThWMTIuMjcxNVoiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMuOTUyNjQgNikiIGZpbGw9IndoaXRlIi8+Cjwvc3ZnPgo=);
  --jp-icon-text-editor: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtdGV4dC1lZGl0b3ItaWNvbi1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xNSAxNUgzdjJoMTJ2LTJ6bTAtOEgzdjJoMTJWN3pNMyAxM2gxOHYtMkgzdjJ6bTAgOGgxOHYtMkgzdjJ6TTMgM3YyaDE4VjNIM3oiLz4KPC9zdmc+Cg==);
  --jp-icon-toc: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik03LDVIMjFWN0g3VjVNNywxM1YxMUgyMVYxM0g3TTQsNC41QTEuNSwxLjUgMCAwLDEgNS41LDZBMS41LDEuNSAwIDAsMSA0LDcuNUExLjUsMS41IDAgMCwxIDIuNSw2QTEuNSwxLjUgMCAwLDEgNCw0LjVNNCwxMC41QTEuNSwxLjUgMCAwLDEgNS41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMy41QTEuNSwxLjUgMCAwLDEgMi41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMC41TTcsMTlWMTdIMjFWMTlIN000LDE2LjVBMS41LDEuNSAwIDAsMSA1LjUsMThBMS41LDEuNSAwIDAsMSA0LDE5LjVBMS41LDEuNSAwIDAsMSAyLjUsMThBMS41LDEuNSAwIDAsMSA0LDE2LjVaIiAvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tree-view: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMiAxMVYzaC03djNIOVYzSDJ2OGg3VjhoMnYxMGg0djNoN3YtOGgtN3YzaC0yVjhoMnYzeiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMiAxNy4xODQ0IDIuOTY5NjggMTQuMzAzMiAxLjg2MDk0IDExLjQ0MDlaIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiMzMzMzMzMiIHN0cm9rZT0iIzMzMzMzMyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOCA5Ljg2NzE5KSIgZD0iTTIuODYwMTUgNC44NjUzNUwwLjcyNjU0OSAyLjk5OTU5TDAgMy42MzA0NUwyLjg2MDE1IDYuMTMxNTdMOCAwLjYzMDg3Mkw3LjI3ODU3IDBMMi44NjAxNSA0Ljg2NTM1WiIvPgo8L3N2Zz4K);
  --jp-icon-undo: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjUgOGMtMi42NSAwLTUuMDUuOTktNi45IDIuNkwyIDd2OWg5bC0zLjYyLTMuNjJjMS4zOS0xLjE2IDMuMTYtMS44OCA1LjEyLTEuODggMy41NCAwIDYuNTUgMi4zMSA3LjYgNS41bDIuMzctLjc4QzIxLjA4IDExLjAzIDE3LjE1IDggMTIuNSA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-user: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE2IDdhNCA0IDAgMTEtOCAwIDQgNCAwIDAxOCAwek0xMiAxNGE3IDcgMCAwMC03IDdoMTRhNyA3IDAgMDAtNy03eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-users: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZlcnNpb249IjEuMSIgdmlld0JveD0iMCAwIDM2IDI0IiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPgogPGcgY2xhc3M9ImpwLWljb24zIiB0cmFuc2Zvcm09Im1hdHJpeCgxLjczMjcgMCAwIDEuNzMyNyAtMy42MjgyIC4wOTk1NzcpIiBmaWxsPSIjNjE2MTYxIj4KICA8cGF0aCB0cmFuc2Zvcm09Im1hdHJpeCgxLjUsMCwwLDEuNSwwLC02KSIgZD0ibTEyLjE4NiA3LjUwOThjLTEuMDUzNSAwLTEuOTc1NyAwLjU2NjUtMi40Nzg1IDEuNDEwMiAwLjc1MDYxIDAuMzEyNzcgMS4zOTc0IDAuODI2NDggMS44NzMgMS40NzI3aDMuNDg2M2MwLTEuNTkyLTEuMjg4OS0yLjg4MjgtMi44ODA5LTIuODgyOHoiLz4KICA8cGF0aCBkPSJtMjAuNDY1IDIuMzg5NWEyLjE4ODUgMi4xODg1IDAgMCAxLTIuMTg4NCAyLjE4ODUgMi4xODg1IDIuMTg4NSAwIDAgMS0yLjE4ODUtMi4xODg1IDIuMTg4NSAyLjE4ODUgMCAwIDEgMi4xODg1LTIuMTg4NSAyLjE4ODUgMi4xODg1IDAgMCAxIDIuMTg4NCAyLjE4ODV6Ii8+CiAgPHBhdGggdHJhbnNmb3JtPSJtYXRyaXgoMS41LDAsMCwxLjUsMCwtNikiIGQ9Im0zLjU4OTggOC40MjE5Yy0xLjExMjYgMC0yLjAxMzcgMC45MDExMS0yLjAxMzcgMi4wMTM3aDIuODE0NWMwLjI2Nzk3LTAuMzczMDkgMC41OTA3LTAuNzA0MzUgMC45NTg5OC0wLjk3ODUyLTAuMzQ0MzMtMC42MTY4OC0xLjAwMzEtMS4wMzUyLTEuNzU5OC0xLjAzNTJ6Ii8+CiAgPHBhdGggZD0ibTYuOTE1NCA0LjYyM2ExLjUyOTQgMS41Mjk0IDAgMCAxLTEuNTI5NCAxLjUyOTQgMS41Mjk0IDEuNTI5NCAwIDAgMS0xLjUyOTQtMS41Mjk0IDEuNTI5NCAxLjUyOTQgMCAwIDEgMS41Mjk0LTEuNTI5NCAxLjUyOTQgMS41Mjk0IDAgMCAxIDEuNTI5NCAxLjUyOTR6Ii8+CiAgPHBhdGggZD0ibTYuMTM1IDEzLjUzNWMwLTMuMjM5MiAyLjYyNTktNS44NjUgNS44NjUtNS44NjUgMy4yMzkyIDAgNS44NjUgMi42MjU5IDUuODY1IDUuODY1eiIvPgogIDxjaXJjbGUgY3g9IjEyIiBjeT0iMy43Njg1IiByPSIyLjk2ODUiLz4KIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-vega: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbjEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjEyMTIxIj4KICAgIDxwYXRoIGQ9Ik0xMC42IDUuNGwyLjItMy4ySDIuMnY3LjNsNC02LjZ6Ii8+CiAgICA8cGF0aCBkPSJNMTUuOCAyLjJsLTQuNCA2LjZMNyA2LjNsLTQuOCA4djUuNWgxNy42VjIuMmgtNHptLTcgMTUuNEg1LjV2LTQuNGgzLjN2NC40em00LjQgMEg5LjhWOS44aDMuNHY3Ljh6bTQuNCAwaC0zLjRWNi41aDMuNHYxMS4xeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-word: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KIDxnIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzQxNDE0MSI+CiAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiA8L2c+CiA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSguNDMgLjA0MDEpIiBmaWxsPSIjZmZmIj4KICA8cGF0aCBkPSJtNC4xNCA4Ljc2cTAuMDY4Mi0xLjg5IDIuNDItMS44OSAxLjE2IDAgMS42OCAwLjQyIDAuNTY3IDAuNDEgMC41NjcgMS4xNnYzLjQ3cTAgMC40NjIgMC41MTQgMC40NjIgMC4xMDMgMCAwLjItMC4wMjMxdjAuNzE0cS0wLjM5OSAwLjEwMy0wLjY1MSAwLjEwMy0wLjQ1MiAwLTAuNjkzLTAuMjItMC4yMzEtMC4yLTAuMjg0LTAuNjYyLTAuOTU2IDAuODcyLTIgMC44NzItMC45MDMgMC0xLjQ3LTAuNDcyLTAuNTI1LTAuNDcyLTAuNTI1LTEuMjYgMC0wLjI2MiAwLjA0NTItMC40NzIgMC4wNTY3LTAuMjIgMC4xMTYtMC4zNzggMC4wNjgyLTAuMTY4IDAuMjMxLTAuMzA0IDAuMTU4LTAuMTQ3IDAuMjYyLTAuMjQyIDAuMTE2LTAuMDkxNCAwLjM2OC0wLjE2OCAwLjI2Mi0wLjA5MTQgMC4zOTktMC4xMjYgMC4xMzYtMC4wNDUyIDAuNDcyLTAuMTAzIDAuMzM2LTAuMDU3OCAwLjUwNC0wLjA3OTggMC4xNTgtMC4wMjMxIDAuNTY3LTAuMDc5OCAwLjU1Ni0wLjA2ODIgMC43NzctMC4yMjEgMC4yMi0wLjE1MiAwLjIyLTAuNDQxdi0wLjI1MnEwLTAuNDMtMC4zNTctMC42NjItMC4zMzYtMC4yMzEtMC45NzYtMC4yMzEtMC42NjIgMC0wLjk5OCAwLjI2Mi0wLjMzNiAwLjI1Mi0wLjM5OSAwLjc5OHptMS44OSAzLjY4cTAuNzg4IDAgMS4yNi0wLjQxIDAuNTA0LTAuNDIgMC41MDQtMC45MDN2LTEuMDVxLTAuMjg0IDAuMTM2LTAuODYxIDAuMjMxLTAuNTY3IDAuMDkxNC0wLjk4NyAwLjE1OC0wLjQyIDAuMDY4Mi0wLjc2NiAwLjMyNi0wLjMzNiAwLjI1Mi0wLjMzNiAwLjcwNHQwLjMwNCAwLjcwNCAwLjg2MSAwLjI1MnoiIHN0cm9rZS13aWR0aD0iMS4wNSIvPgogIDxwYXRoIGQ9Im0xMCA0LjU2aDAuOTQ1djMuMTVxMC42NTEtMC45NzYgMS44OS0wLjk3NiAxLjE2IDAgMS44OSAwLjg0IDAuNjgyIDAuODQgMC42ODIgMi4zMSAwIDEuNDctMC43MDQgMi40Mi0wLjcwNCAwLjg4Mi0xLjg5IDAuODgyLTEuMjYgMC0xLjg5LTEuMDJ2MC43NjZoLTAuODV6bTIuNjIgMy4wNHEtMC43NDYgMC0xLjE2IDAuNjQtMC40NTIgMC42My0wLjQ1MiAxLjY4IDAgMS4wNSAwLjQ1MiAxLjY4dDEuMTYgMC42M3EwLjc3NyAwIDEuMjYtMC42MyAwLjQ5NC0wLjY0IDAuNDk0LTEuNjggMC0xLjA1LTAuNDcyLTEuNjgtMC40NjItMC42NC0xLjI2LTAuNjR6IiBzdHJva2Utd2lkdGg9IjEuMDUiLz4KICA8cGF0aCBkPSJtMi43MyAxNS44IDEzLjYgMC4wMDgxYzAuMDA2OSAwIDAtMi42IDAtMi42IDAtMC4wMDc4LTEuMTUgMC0xLjE1IDAtMC4wMDY5IDAtMC4wMDgzIDEuNS0wLjAwODMgMS41LTJlLTMgLTAuMDAxNC0xMS4zLTAuMDAxNC0xMS4zLTAuMDAxNGwtMC4wMDU5Mi0xLjVjMC0wLjAwNzgtMS4xNyAwLjAwMTMtMS4xNyAwLjAwMTN6IiBzdHJva2Utd2lkdGg9Ii45NzUiLz4KIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-yaml: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1jb250cmFzdDIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjRDgxQjYwIj4KICAgIDxwYXRoIGQ9Ik03LjIgMTguNnYtNS40TDMgNS42aDMuM2wxLjQgMy4xYy4zLjkuNiAxLjYgMSAyLjUuMy0uOC42LTEuNiAxLTIuNWwxLjQtMy4xaDMuNGwtNC40IDcuNnY1LjVsLTIuOS0uMXoiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxNi41IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxMSIgcj0iMi4xIi8+CiAgPC9nPgo8L3N2Zz4K);
}

/* Icon CSS class declarations */

.jp-AddAboveIcon {
  background-image: var(--jp-icon-add-above);
}

.jp-AddBelowIcon {
  background-image: var(--jp-icon-add-below);
}

.jp-AddIcon {
  background-image: var(--jp-icon-add);
}

.jp-BellIcon {
  background-image: var(--jp-icon-bell);
}

.jp-BugDotIcon {
  background-image: var(--jp-icon-bug-dot);
}

.jp-BugIcon {
  background-image: var(--jp-icon-bug);
}

.jp-BuildIcon {
  background-image: var(--jp-icon-build);
}

.jp-CaretDownEmptyIcon {
  background-image: var(--jp-icon-caret-down-empty);
}

.jp-CaretDownEmptyThinIcon {
  background-image: var(--jp-icon-caret-down-empty-thin);
}

.jp-CaretDownIcon {
  background-image: var(--jp-icon-caret-down);
}

.jp-CaretLeftIcon {
  background-image: var(--jp-icon-caret-left);
}

.jp-CaretRightIcon {
  background-image: var(--jp-icon-caret-right);
}

.jp-CaretUpEmptyThinIcon {
  background-image: var(--jp-icon-caret-up-empty-thin);
}

.jp-CaretUpIcon {
  background-image: var(--jp-icon-caret-up);
}

.jp-CaseSensitiveIcon {
  background-image: var(--jp-icon-case-sensitive);
}

.jp-CheckIcon {
  background-image: var(--jp-icon-check);
}

.jp-CircleEmptyIcon {
  background-image: var(--jp-icon-circle-empty);
}

.jp-CircleIcon {
  background-image: var(--jp-icon-circle);
}

.jp-ClearIcon {
  background-image: var(--jp-icon-clear);
}

.jp-CloseIcon {
  background-image: var(--jp-icon-close);
}

.jp-CodeCheckIcon {
  background-image: var(--jp-icon-code-check);
}

.jp-CodeIcon {
  background-image: var(--jp-icon-code);
}

.jp-CollapseAllIcon {
  background-image: var(--jp-icon-collapse-all);
}

.jp-ConsoleIcon {
  background-image: var(--jp-icon-console);
}

.jp-CopyIcon {
  background-image: var(--jp-icon-copy);
}

.jp-CopyrightIcon {
  background-image: var(--jp-icon-copyright);
}

.jp-CutIcon {
  background-image: var(--jp-icon-cut);
}

.jp-DeleteIcon {
  background-image: var(--jp-icon-delete);
}

.jp-DownloadIcon {
  background-image: var(--jp-icon-download);
}

.jp-DuplicateIcon {
  background-image: var(--jp-icon-duplicate);
}

.jp-EditIcon {
  background-image: var(--jp-icon-edit);
}

.jp-EllipsesIcon {
  background-image: var(--jp-icon-ellipses);
}

.jp-ErrorIcon {
  background-image: var(--jp-icon-error);
}

.jp-ExpandAllIcon {
  background-image: var(--jp-icon-expand-all);
}

.jp-ExtensionIcon {
  background-image: var(--jp-icon-extension);
}

.jp-FastForwardIcon {
  background-image: var(--jp-icon-fast-forward);
}

.jp-FileIcon {
  background-image: var(--jp-icon-file);
}

.jp-FileUploadIcon {
  background-image: var(--jp-icon-file-upload);
}

.jp-FilterDotIcon {
  background-image: var(--jp-icon-filter-dot);
}

.jp-FilterIcon {
  background-image: var(--jp-icon-filter);
}

.jp-FilterListIcon {
  background-image: var(--jp-icon-filter-list);
}

.jp-FolderFavoriteIcon {
  background-image: var(--jp-icon-folder-favorite);
}

.jp-FolderIcon {
  background-image: var(--jp-icon-folder);
}

.jp-HomeIcon {
  background-image: var(--jp-icon-home);
}

.jp-Html5Icon {
  background-image: var(--jp-icon-html5);
}

.jp-ImageIcon {
  background-image: var(--jp-icon-image);
}

.jp-InfoIcon {
  background-image: var(--jp-icon-info);
}

.jp-InspectorIcon {
  background-image: var(--jp-icon-inspector);
}

.jp-JsonIcon {
  background-image: var(--jp-icon-json);
}

.jp-JuliaIcon {
  background-image: var(--jp-icon-julia);
}

.jp-JupyterFaviconIcon {
  background-image: var(--jp-icon-jupyter-favicon);
}

.jp-JupyterIcon {
  background-image: var(--jp-icon-jupyter);
}

.jp-JupyterlabWordmarkIcon {
  background-image: var(--jp-icon-jupyterlab-wordmark);
}

.jp-KernelIcon {
  background-image: var(--jp-icon-kernel);
}

.jp-KeyboardIcon {
  background-image: var(--jp-icon-keyboard);
}

.jp-LaunchIcon {
  background-image: var(--jp-icon-launch);
}

.jp-LauncherIcon {
  background-image: var(--jp-icon-launcher);
}

.jp-LineFormIcon {
  background-image: var(--jp-icon-line-form);
}

.jp-LinkIcon {
  background-image: var(--jp-icon-link);
}

.jp-ListIcon {
  background-image: var(--jp-icon-list);
}

.jp-MarkdownIcon {
  background-image: var(--jp-icon-markdown);
}

.jp-MoveDownIcon {
  background-image: var(--jp-icon-move-down);
}

.jp-MoveUpIcon {
  background-image: var(--jp-icon-move-up);
}

.jp-NewFolderIcon {
  background-image: var(--jp-icon-new-folder);
}

.jp-NotTrustedIcon {
  background-image: var(--jp-icon-not-trusted);
}

.jp-NotebookIcon {
  background-image: var(--jp-icon-notebook);
}

.jp-NumberingIcon {
  background-image: var(--jp-icon-numbering);
}

.jp-OfflineBoltIcon {
  background-image: var(--jp-icon-offline-bolt);
}

.jp-PaletteIcon {
  background-image: var(--jp-icon-palette);
}

.jp-PasteIcon {
  background-image: var(--jp-icon-paste);
}

.jp-PdfIcon {
  background-image: var(--jp-icon-pdf);
}

.jp-PythonIcon {
  background-image: var(--jp-icon-python);
}

.jp-RKernelIcon {
  background-image: var(--jp-icon-r-kernel);
}

.jp-ReactIcon {
  background-image: var(--jp-icon-react);
}

.jp-RedoIcon {
  background-image: var(--jp-icon-redo);
}

.jp-RefreshIcon {
  background-image: var(--jp-icon-refresh);
}

.jp-RegexIcon {
  background-image: var(--jp-icon-regex);
}

.jp-RunIcon {
  background-image: var(--jp-icon-run);
}

.jp-RunningIcon {
  background-image: var(--jp-icon-running);
}

.jp-SaveIcon {
  background-image: var(--jp-icon-save);
}

.jp-SearchIcon {
  background-image: var(--jp-icon-search);
}

.jp-SettingsIcon {
  background-image: var(--jp-icon-settings);
}

.jp-ShareIcon {
  background-image: var(--jp-icon-share);
}

.jp-SpreadsheetIcon {
  background-image: var(--jp-icon-spreadsheet);
}

.jp-StopIcon {
  background-image: var(--jp-icon-stop);
}

.jp-TabIcon {
  background-image: var(--jp-icon-tab);
}

.jp-TableRowsIcon {
  background-image: var(--jp-icon-table-rows);
}

.jp-TagIcon {
  background-image: var(--jp-icon-tag);
}

.jp-TerminalIcon {
  background-image: var(--jp-icon-terminal);
}

.jp-TextEditorIcon {
  background-image: var(--jp-icon-text-editor);
}

.jp-TocIcon {
  background-image: var(--jp-icon-toc);
}

.jp-TreeViewIcon {
  background-image: var(--jp-icon-tree-view);
}

.jp-TrustedIcon {
  background-image: var(--jp-icon-trusted);
}

.jp-UndoIcon {
  background-image: var(--jp-icon-undo);
}

.jp-UserIcon {
  background-image: var(--jp-icon-user);
}

.jp-UsersIcon {
  background-image: var(--jp-icon-users);
}

.jp-VegaIcon {
  background-image: var(--jp-icon-vega);
}

.jp-WordIcon {
  background-image: var(--jp-icon-word);
}

.jp-YamlIcon {
  background-image: var(--jp-icon-yaml);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

.jp-Icon,
.jp-MaterialIcon {
  background-position: center;
  background-repeat: no-repeat;
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-cover {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

/**
 * (DEPRECATED) Support for specific CSS icon sizes
 */

.jp-Icon-16 {
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-18 {
  background-size: 18px;
  min-width: 18px;
  min-height: 18px;
}

.jp-Icon-20 {
  background-size: 20px;
  min-width: 20px;
  min-height: 20px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.lm-TabBar .lm-TabBar-addButton {
  align-items: center;
  display: flex;
  padding: 4px;
  padding-bottom: 5px;
  margin-right: 1px;
  background-color: var(--jp-layout-color2);
}

.lm-TabBar .lm-TabBar-addButton:hover {
  background-color: var(--jp-layout-color1);
}

.lm-DockPanel-tabBar .lm-TabBar-tab {
  width: var(--jp-private-horizontal-tab-width);
}

.lm-DockPanel-tabBar .lm-TabBar-content {
  flex: unset;
}

.lm-DockPanel-tabBar[data-orientation='horizontal'] {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for icons as inline SVG HTMLElements
 */

/* recolor the primary elements of an icon */
.jp-icon0[fill] {
  fill: var(--jp-inverse-layout-color0);
}

.jp-icon1[fill] {
  fill: var(--jp-inverse-layout-color1);
}

.jp-icon2[fill] {
  fill: var(--jp-inverse-layout-color2);
}

.jp-icon3[fill] {
  fill: var(--jp-inverse-layout-color3);
}

.jp-icon4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}

.jp-icon1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}

.jp-icon2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}

.jp-icon3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}

.jp-icon4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-accent0[fill] {
  fill: var(--jp-layout-color0);
}

.jp-icon-accent1[fill] {
  fill: var(--jp-layout-color1);
}

.jp-icon-accent2[fill] {
  fill: var(--jp-layout-color2);
}

.jp-icon-accent3[fill] {
  fill: var(--jp-layout-color3);
}

.jp-icon-accent4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-accent0[stroke] {
  stroke: var(--jp-layout-color0);
}

.jp-icon-accent1[stroke] {
  stroke: var(--jp-layout-color1);
}

.jp-icon-accent2[stroke] {
  stroke: var(--jp-layout-color2);
}

.jp-icon-accent3[stroke] {
  stroke: var(--jp-layout-color3);
}

.jp-icon-accent4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-none[fill] {
  fill: none;
}

.jp-icon-none[stroke] {
  stroke: none;
}

/* brand icon colors. Same for light and dark */
.jp-icon-brand0[fill] {
  fill: var(--jp-brand-color0);
}

.jp-icon-brand1[fill] {
  fill: var(--jp-brand-color1);
}

.jp-icon-brand2[fill] {
  fill: var(--jp-brand-color2);
}

.jp-icon-brand3[fill] {
  fill: var(--jp-brand-color3);
}

.jp-icon-brand4[fill] {
  fill: var(--jp-brand-color4);
}

.jp-icon-brand0[stroke] {
  stroke: var(--jp-brand-color0);
}

.jp-icon-brand1[stroke] {
  stroke: var(--jp-brand-color1);
}

.jp-icon-brand2[stroke] {
  stroke: var(--jp-brand-color2);
}

.jp-icon-brand3[stroke] {
  stroke: var(--jp-brand-color3);
}

.jp-icon-brand4[stroke] {
  stroke: var(--jp-brand-color4);
}

/* warn icon colors. Same for light and dark */
.jp-icon-warn0[fill] {
  fill: var(--jp-warn-color0);
}

.jp-icon-warn1[fill] {
  fill: var(--jp-warn-color1);
}

.jp-icon-warn2[fill] {
  fill: var(--jp-warn-color2);
}

.jp-icon-warn3[fill] {
  fill: var(--jp-warn-color3);
}

.jp-icon-warn0[stroke] {
  stroke: var(--jp-warn-color0);
}

.jp-icon-warn1[stroke] {
  stroke: var(--jp-warn-color1);
}

.jp-icon-warn2[stroke] {
  stroke: var(--jp-warn-color2);
}

.jp-icon-warn3[stroke] {
  stroke: var(--jp-warn-color3);
}

/* icon colors that contrast well with each other and most backgrounds */
.jp-icon-contrast0[fill] {
  fill: var(--jp-icon-contrast-color0);
}

.jp-icon-contrast1[fill] {
  fill: var(--jp-icon-contrast-color1);
}

.jp-icon-contrast2[fill] {
  fill: var(--jp-icon-contrast-color2);
}

.jp-icon-contrast3[fill] {
  fill: var(--jp-icon-contrast-color3);
}

.jp-icon-contrast0[stroke] {
  stroke: var(--jp-icon-contrast-color0);
}

.jp-icon-contrast1[stroke] {
  stroke: var(--jp-icon-contrast-color1);
}

.jp-icon-contrast2[stroke] {
  stroke: var(--jp-icon-contrast-color2);
}

.jp-icon-contrast3[stroke] {
  stroke: var(--jp-icon-contrast-color3);
}

.jp-icon-dot[fill] {
  fill: var(--jp-warn-color0);
}

.jp-jupyter-icon-color[fill] {
  fill: var(--jp-jupyter-icon-color, var(--jp-warn-color0));
}

.jp-notebook-icon-color[fill] {
  fill: var(--jp-notebook-icon-color, var(--jp-warn-color0));
}

.jp-json-icon-color[fill] {
  fill: var(--jp-json-icon-color, var(--jp-warn-color1));
}

.jp-console-icon-color[fill] {
  fill: var(--jp-console-icon-color, white);
}

.jp-console-icon-background-color[fill] {
  fill: var(--jp-console-icon-background-color, var(--jp-brand-color1));
}

.jp-terminal-icon-color[fill] {
  fill: var(--jp-terminal-icon-color, var(--jp-layout-color2));
}

.jp-terminal-icon-background-color[fill] {
  fill: var(
    --jp-terminal-icon-background-color,
    var(--jp-inverse-layout-color2)
  );
}

.jp-text-editor-icon-color[fill] {
  fill: var(--jp-text-editor-icon-color, var(--jp-inverse-layout-color3));
}

.jp-inspector-icon-color[fill] {
  fill: var(--jp-inspector-icon-color, var(--jp-inverse-layout-color3));
}

/* CSS for icons in selected filebrowser listing items */
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

.jp-DirListing-item.jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* stylelint-disable selector-max-class, selector-max-compound-selectors */

/**
* TODO: come up with non css-hack solution for showing the busy icon on top
*  of the close icon
* CSS for complex behavior of close icon of tabs in the main area tabbar
*/
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}

.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

/* stylelint-enable selector-max-class, selector-max-compound-selectors */

/* CSS for icons in status bar */
#jp-main-statusbar .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

#jp-main-statusbar .jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* special handling for splash icon CSS. While the theme CSS reloads during
   splash, the splash icon can loose theming. To prevent that, we set a
   default for its color variable */
:root {
  --jp-warn-color0: var(--md-orange-700);
}

/* not sure what to do with this one, used in filebrowser listing */
.jp-DragIcon {
  margin-right: 4px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for alt colors for icons as inline SVG HTMLElements
 */

/* alt recolor the primary elements of an icon */
.jp-icon-alt .jp-icon0[fill] {
  fill: var(--jp-layout-color0);
}

.jp-icon-alt .jp-icon1[fill] {
  fill: var(--jp-layout-color1);
}

.jp-icon-alt .jp-icon2[fill] {
  fill: var(--jp-layout-color2);
}

.jp-icon-alt .jp-icon3[fill] {
  fill: var(--jp-layout-color3);
}

.jp-icon-alt .jp-icon4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-alt .jp-icon0[stroke] {
  stroke: var(--jp-layout-color0);
}

.jp-icon-alt .jp-icon1[stroke] {
  stroke: var(--jp-layout-color1);
}

.jp-icon-alt .jp-icon2[stroke] {
  stroke: var(--jp-layout-color2);
}

.jp-icon-alt .jp-icon3[stroke] {
  stroke: var(--jp-layout-color3);
}

.jp-icon-alt .jp-icon4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* alt recolor the accent elements of an icon */
.jp-icon-alt .jp-icon-accent0[fill] {
  fill: var(--jp-inverse-layout-color0);
}

.jp-icon-alt .jp-icon-accent1[fill] {
  fill: var(--jp-inverse-layout-color1);
}

.jp-icon-alt .jp-icon-accent2[fill] {
  fill: var(--jp-inverse-layout-color2);
}

.jp-icon-alt .jp-icon-accent3[fill] {
  fill: var(--jp-inverse-layout-color3);
}

.jp-icon-alt .jp-icon-accent4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-alt .jp-icon-accent0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}

.jp-icon-alt .jp-icon-accent1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}

.jp-icon-alt .jp-icon-accent2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}

.jp-icon-alt .jp-icon-accent3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}

.jp-icon-alt .jp-icon-accent4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-icon-hoverShow:not(:hover) .jp-icon-hoverShow-content {
  display: none !important;
}

/**
 * Support for hover colors for icons as inline SVG HTMLElements
 */

/**
 * regular colors
 */

/* recolor the primary elements of an icon */
.jp-icon-hover :hover .jp-icon0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}

.jp-icon-hover :hover .jp-icon1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}

.jp-icon-hover :hover .jp-icon2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}

.jp-icon-hover :hover .jp-icon3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}

.jp-icon-hover :hover .jp-icon4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}

.jp-icon-hover :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}

.jp-icon-hover :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}

.jp-icon-hover :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}

.jp-icon-hover :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-hover :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-layout-color0);
}

.jp-icon-hover :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-layout-color1);
}

.jp-icon-hover :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-layout-color2);
}

.jp-icon-hover :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-layout-color3);
}

.jp-icon-hover :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}

.jp-icon-hover :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}

.jp-icon-hover :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}

.jp-icon-hover :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}

.jp-icon-hover :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-hover :hover .jp-icon-none-hover[fill] {
  fill: none;
}

.jp-icon-hover :hover .jp-icon-none-hover[stroke] {
  stroke: none;
}

/**
 * inverse colors
 */

/* inverse recolor the primary elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[fill] {
  fill: var(--jp-layout-color0);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[fill] {
  fill: var(--jp-layout-color1);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[fill] {
  fill: var(--jp-layout-color2);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[fill] {
  fill: var(--jp-layout-color3);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* inverse recolor the accent elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-IFrame {
  width: 100%;
  height: 100%;
}

.jp-IFrame > iframe {
  border: none;
}

/*
When drag events occur, `lm-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-IFrame {
  position: relative;
}

body.lm-mod-override-cursor .jp-IFrame::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-HoverBox {
  position: fixed;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FormGroup-content fieldset {
  border: none;
  padding: 0;
  min-width: 0;
  width: 100%;
}

/* stylelint-disable selector-max-type */

.jp-FormGroup-content fieldset .jp-inputFieldWrapper input,
.jp-FormGroup-content fieldset .jp-inputFieldWrapper select,
.jp-FormGroup-content fieldset .jp-inputFieldWrapper textarea {
  font-size: var(--jp-content-font-size2);
  border-color: var(--jp-input-border-color);
  border-style: solid;
  border-radius: var(--jp-border-radius);
  border-width: 1px;
  padding: 6px 8px;
  background: none;
  color: var(--jp-ui-font-color0);
  height: inherit;
}

.jp-FormGroup-content fieldset input[type='checkbox'] {
  position: relative;
  top: 2px;
  margin-left: 0;
}

.jp-FormGroup-content button.jp-mod-styled {
  cursor: pointer;
}

.jp-FormGroup-content .checkbox label {
  cursor: pointer;
  font-size: var(--jp-content-font-size1);
}

.jp-FormGroup-content .jp-root > fieldset > legend {
  display: none;
}

.jp-FormGroup-content .jp-root > fieldset > p {
  display: none;
}

/** copy of `input.jp-mod-styled:focus` style */
.jp-FormGroup-content fieldset input:focus,
.jp-FormGroup-content fieldset select:focus {
  -moz-outline-radius: unset;
  outline: var(--jp-border-width) solid var(--md-blue-500);
  outline-offset: -1px;
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-FormGroup-content fieldset input:hover:not(:focus),
.jp-FormGroup-content fieldset select:hover:not(:focus) {
  background-color: var(--jp-border-color2);
}

/* stylelint-enable selector-max-type */

.jp-FormGroup-content .checkbox .field-description {
  /* Disable default description field for checkbox:
   because other widgets do not have description fields,
   we add descriptions to each widget on the field level.
  */
  display: none;
}

.jp-FormGroup-content #root__description {
  display: none;
}

.jp-FormGroup-content .jp-modifiedIndicator {
  width: 5px;
  background-color: var(--jp-brand-color2);
  margin-top: 0;
  margin-left: calc(var(--jp-private-settingeditor-modifier-indent) * -1);
  flex-shrink: 0;
}

.jp-FormGroup-content .jp-modifiedIndicator.jp-errorIndicator {
  background-color: var(--jp-error-color0);
  margin-right: 0.5em;
}

/* RJSF ARRAY style */

.jp-arrayFieldWrapper legend {
  font-size: var(--jp-content-font-size2);
  color: var(--jp-ui-font-color0);
  flex-basis: 100%;
  padding: 4px 0;
  font-weight: var(--jp-content-heading-font-weight);
  border-bottom: 1px solid var(--jp-border-color2);
}

.jp-arrayFieldWrapper .field-description {
  padding: 4px 0;
  white-space: pre-wrap;
}

.jp-arrayFieldWrapper .array-item {
  width: 100%;
  border: 1px solid var(--jp-border-color2);
  border-radius: 4px;
  margin: 4px;
}

.jp-ArrayOperations {
  display: flex;
  margin-left: 8px;
}

.jp-ArrayOperationsButton {
  margin: 2px;
}

.jp-ArrayOperationsButton .jp-icon3[fill] {
  fill: var(--jp-ui-font-color0);
}

button.jp-ArrayOperationsButton.jp-mod-styled:disabled {
  cursor: not-allowed;
  opacity: 0.5;
}

/* RJSF form validation error */

.jp-FormGroup-content .validationErrors {
  color: var(--jp-error-color0);
}

/* Hide panel level error as duplicated the field level error */
.jp-FormGroup-content .panel.errors {
  display: none;
}

/* RJSF normal content (settings-editor) */

.jp-FormGroup-contentNormal {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}

.jp-FormGroup-contentNormal .jp-FormGroup-contentItem {
  margin-left: 7px;
  color: var(--jp-ui-font-color0);
}

.jp-FormGroup-contentNormal .jp-FormGroup-description {
  flex-basis: 100%;
  padding: 4px 7px;
}

.jp-FormGroup-contentNormal .jp-FormGroup-default {
  flex-basis: 100%;
  padding: 4px 7px;
}

.jp-FormGroup-contentNormal .jp-FormGroup-fieldLabel {
  font-size: var(--jp-content-font-size1);
  font-weight: normal;
  min-width: 120px;
}

.jp-FormGroup-contentNormal fieldset:not(:first-child) {
  margin-left: 7px;
}

.jp-FormGroup-contentNormal .field-array-of-string .array-item {
  /* Display `jp-ArrayOperations` buttons side-by-side with content except
    for small screens where flex-wrap will place them one below the other.
  */
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}

.jp-FormGroup-contentNormal .jp-objectFieldWrapper .form-group {
  padding: 2px 8px 2px var(--jp-private-settingeditor-modifier-indent);
  margin-top: 2px;
}

/* RJSF compact content (metadata-form) */

.jp-FormGroup-content.jp-FormGroup-contentCompact {
  width: 100%;
}

.jp-FormGroup-contentCompact .form-group {
  display: flex;
  padding: 0.5em 0.2em 0.5em 0;
}

.jp-FormGroup-contentCompact
  .jp-FormGroup-compactTitle
  .jp-FormGroup-description {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color2);
}

.jp-FormGroup-contentCompact .jp-FormGroup-fieldLabel {
  padding-bottom: 0.3em;
}

.jp-FormGroup-contentCompact .jp-inputFieldWrapper .form-control {
  width: 100%;
  box-sizing: border-box;
}

.jp-FormGroup-contentCompact .jp-arrayFieldWrapper .jp-FormGroup-compactTitle {
  padding-bottom: 7px;
}

.jp-FormGroup-contentCompact
  .jp-objectFieldWrapper
  .jp-objectFieldWrapper
  .form-group {
  padding: 2px 8px 2px var(--jp-private-settingeditor-modifier-indent);
  margin-top: 2px;
}

.jp-FormGroup-contentCompact ul.error-detail {
  margin-block-start: 0.5em;
  margin-block-end: 0.5em;
  padding-inline-start: 1em;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-SidePanel {
  display: flex;
  flex-direction: column;
  min-width: var(--jp-sidebar-min-width);
  overflow-y: auto;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  font-size: var(--jp-ui-font-size1);
}

.jp-SidePanel-header {
  flex: 0 0 auto;
  display: flex;
  border-bottom: var(--jp-border-width) solid var(--jp-border-color2);
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin: 0;
  padding: 2px;
  text-transform: uppercase;
}

.jp-SidePanel-toolbar {
  flex: 0 0 auto;
}

.jp-SidePanel-content {
  flex: 1 1 auto;
}

.jp-SidePanel-toolbar,
.jp-AccordionPanel-toolbar {
  height: var(--jp-private-toolbar-height);
}

.jp-SidePanel-toolbar.jp-Toolbar-micro {
  display: none;
}

.lm-AccordionPanel .jp-AccordionPanel-title {
  box-sizing: border-box;
  line-height: 25px;
  margin: 0;
  display: flex;
  align-items: center;
  background: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  font-size: var(--jp-ui-font-size0);
}

.jp-AccordionPanel-title {
  cursor: pointer;
  user-select: none;
  -moz-user-select: none;
  -webkit-user-select: none;
  text-transform: uppercase;
}

.lm-AccordionPanel[data-orientation='horizontal'] > .jp-AccordionPanel-title {
  /* Title is rotated for horizontal accordion panel using CSS */
  display: block;
  transform-origin: top left;
  transform: rotate(-90deg) translate(-100%);
}

.jp-AccordionPanel-title .lm-AccordionPanel-titleLabel {
  user-select: none;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
}

.jp-AccordionPanel-title .lm-AccordionPanel-titleCollapser {
  transform: rotate(-90deg);
  margin: auto 0;
  height: 16px;
}

.jp-AccordionPanel-title.lm-mod-expanded .lm-AccordionPanel-titleCollapser {
  transform: rotate(0deg);
}

.lm-AccordionPanel .jp-AccordionPanel-toolbar {
  background: none;
  box-shadow: none;
  border: none;
  margin-left: auto;
}

.lm-AccordionPanel .lm-SplitPanel-handle:hover {
  background: var(--jp-layout-color3);
}

.jp-text-truncated {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Spinner {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-layout-color0);
  outline: none;
}

.jp-SpinnerContent {
  font-size: 10px;
  margin: 50px auto;
  text-indent: -9999em;
  width: 3em;
  height: 3em;
  border-radius: 50%;
  background: var(--jp-brand-color3);
  background: linear-gradient(
    to right,
    #f37626 10%,
    rgba(255, 255, 255, 0) 42%
  );
  position: relative;
  animation: load3 1s infinite linear, fadeIn 1s;
}

.jp-SpinnerContent::before {
  width: 50%;
  height: 50%;
  background: #f37626;
  border-radius: 100% 0 0;
  position: absolute;
  top: 0;
  left: 0;
  content: '';
}

.jp-SpinnerContent::after {
  background: var(--jp-layout-color0);
  width: 75%;
  height: 75%;
  border-radius: 50%;
  content: '';
  margin: auto;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }
}

@keyframes load3 {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

button.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: none;
  box-sizing: border-box;
  text-align: center;
  line-height: 32px;
  height: 32px;
  padding: 0 12px;
  letter-spacing: 0.8px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled {
  background: var(--jp-input-background);
  height: 28px;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color1);
  padding-left: 7px;
  padding-right: 7px;
  font-size: var(--jp-ui-font-size2);
  color: var(--jp-ui-font-color0);
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input[type='checkbox'].jp-mod-styled {
  appearance: checkbox;
  -webkit-appearance: checkbox;
  -moz-appearance: checkbox;
  height: auto;
}

input.jp-mod-styled:focus {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-select-wrapper {
  display: flex;
  position: relative;
  flex-direction: column;
  padding: 1px;
  background-color: var(--jp-layout-color1);
  box-sizing: border-box;
  margin-bottom: 12px;
}

.jp-select-wrapper:not(.multiple) {
  height: 28px;
}

.jp-select-wrapper.jp-mod-focused select.jp-mod-styled {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-input-active-background);
}

select.jp-mod-styled:hover {
  cursor: pointer;
  color: var(--jp-ui-font-color0);
  background-color: var(--jp-input-hover-background);
  box-shadow: inset 0 0 1px rgba(0, 0, 0, 0.5);
}

select.jp-mod-styled {
  flex: 1 1 auto;
  width: 100%;
  font-size: var(--jp-ui-font-size2);
  background: var(--jp-input-background);
  color: var(--jp-ui-font-color0);
  padding: 0 25px 0 8px;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

select.jp-mod-styled:not([multiple]) {
  height: 32px;
}

select.jp-mod-styled[multiple] {
  max-height: 200px;
  overflow-y: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-switch {
  display: flex;
  align-items: center;
  padding-left: 4px;
  padding-right: 4px;
  font-size: var(--jp-ui-font-size1);
  background-color: transparent;
  color: var(--jp-ui-font-color1);
  border: none;
  height: 20px;
}

.jp-switch:hover {
  background-color: var(--jp-layout-color2);
}

.jp-switch-label {
  margin-right: 5px;
  font-family: var(--jp-ui-font-family);
}

.jp-switch-track {
  cursor: pointer;
  background-color: var(--jp-switch-color, var(--jp-border-color1));
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 34px;
  height: 16px;
  width: 35px;
  position: relative;
}

.jp-switch-track::before {
  content: '';
  position: absolute;
  height: 10px;
  width: 10px;
  margin: 3px;
  left: 0;
  background-color: var(--jp-ui-inverse-font-color1);
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 50%;
}

.jp-switch[aria-checked='true'] .jp-switch-track {
  background-color: var(--jp-switch-true-position-color, var(--jp-warn-color0));
}

.jp-switch[aria-checked='true'] .jp-switch-track::before {
  /* track width (35) - margins (3 + 3) - thumb width (10) */
  left: 19px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toolbar-height: calc(
    28px + var(--jp-border-width)
  ); /* leave 28px for content */
}

.jp-Toolbar {
  color: var(--jp-ui-font-color1);
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: 2px;
  z-index: 8;
  overflow-x: hidden;
}

/* Toolbar items */

.jp-Toolbar > .jp-Toolbar-item.jp-Toolbar-spacer {
  flex-grow: 1;
  flex-shrink: 1;
}

.jp-Toolbar-item.jp-Toolbar-kernelStatus {
  display: inline-block;
  width: 32px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 16px;
}

.jp-Toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  display: flex;
  padding-left: 1px;
  padding-right: 1px;
  font-size: var(--jp-ui-font-size1);
  line-height: var(--jp-private-toolbar-height);
  height: 100%;
}

/* Toolbar buttons */

/* This is the div we use to wrap the react component into a Widget */
div.jp-ToolbarButton {
  color: transparent;
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0;
  margin: 0;
}

button.jp-ToolbarButtonComponent {
  background: var(--jp-layout-color1);
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0 6px;
  margin: 0;
  height: 24px;
  border-radius: var(--jp-border-radius);
  display: flex;
  align-items: center;
  text-align: center;
  font-size: 14px;
  min-width: unset;
  min-height: unset;
}

button.jp-ToolbarButtonComponent:disabled {
  opacity: 0.4;
}

button.jp-ToolbarButtonComponent > span {
  padding: 0;
  flex: 0 0 auto;
}

button.jp-ToolbarButtonComponent .jp-ToolbarButtonComponent-label {
  font-size: var(--jp-ui-font-size1);
  line-height: 100%;
  padding-left: 2px;
  color: var(--jp-ui-font-color1);
  font-family: var(--jp-ui-font-family);
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar.jp-Toolbar-micro {
  padding: 0;
  min-height: 0;
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar {
  border: none;
  box-shadow: none;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-WindowedPanel-outer {
  position: relative;
  overflow-y: auto;
}

.jp-WindowedPanel-inner {
  position: relative;
}

.jp-WindowedPanel-window {
  position: absolute;
  left: 0;
  right: 0;
  overflow: visible;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* Sibling imports */

body {
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
}

/* Disable native link decoration styles everywhere outside of dialog boxes */
a {
  text-decoration: unset;
  color: unset;
}

a:hover {
  text-decoration: unset;
  color: unset;
}

/* Accessibility for links inside dialog box text */
.jp-Dialog-content a {
  text-decoration: revert;
  color: var(--jp-content-link-color);
}

.jp-Dialog-content a:hover {
  text-decoration: revert;
}

/* Styles for ui-components */
.jp-Button {
  color: var(--jp-ui-font-color2);
  border-radius: var(--jp-border-radius);
  padding: 0 12px;
  font-size: var(--jp-ui-font-size1);

  /* Copy from blueprint 3 */
  display: inline-flex;
  flex-direction: row;
  border: none;
  cursor: pointer;
  align-items: center;
  justify-content: center;
  text-align: left;
  vertical-align: middle;
  min-height: 30px;
  min-width: 30px;
}

.jp-Button:disabled {
  cursor: not-allowed;
}

.jp-Button:empty {
  padding: 0 !important;
}

.jp-Button.jp-mod-small {
  min-height: 24px;
  min-width: 24px;
  font-size: 12px;
  padding: 0 7px;
}

/* Use our own theme for hover styles */
.jp-Button.jp-mod-minimal:hover {
  background-color: var(--jp-layout-color2);
}

.jp-Button.jp-mod-minimal {
  background: none;
}

.jp-InputGroup {
  display: block;
  position: relative;
}

.jp-InputGroup input {
  box-sizing: border-box;
  border: none;
  border-radius: 0;
  background-color: transparent;
  color: var(--jp-ui-font-color0);
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
  padding-bottom: 0;
  padding-top: 0;
  padding-left: 10px;
  padding-right: 28px;
  position: relative;
  width: 100%;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  font-size: 14px;
  font-weight: 400;
  height: 30px;
  line-height: 30px;
  outline: none;
  vertical-align: middle;
}

.jp-InputGroup input:focus {
  box-shadow: inset 0 0 0 var(--jp-border-width)
      var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-InputGroup input:disabled {
  cursor: not-allowed;
  resize: block;
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color2);
}

.jp-InputGroup input:disabled ~ span {
  cursor: not-allowed;
  color: var(--jp-ui-font-color2);
}

.jp-InputGroup input::placeholder,
input::placeholder {
  color: var(--jp-ui-font-color2);
}

.jp-InputGroupAction {
  position: absolute;
  bottom: 1px;
  right: 0;
  padding: 6px;
}

.jp-HTMLSelect.jp-DefaultStyle select {
  background-color: initial;
  border: none;
  border-radius: 0;
  box-shadow: none;
  color: var(--jp-ui-font-color0);
  display: block;
  font-size: var(--jp-ui-font-size1);
  font-family: var(--jp-ui-font-family);
  height: 24px;
  line-height: 14px;
  padding: 0 25px 0 10px;
  text-align: left;
  -moz-appearance: none;
  -webkit-appearance: none;
}

.jp-HTMLSelect.jp-DefaultStyle select:disabled {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color2);
  cursor: not-allowed;
  resize: block;
}

.jp-HTMLSelect.jp-DefaultStyle select:disabled ~ span {
  cursor: not-allowed;
}

/* Use our own theme for hover and option styles */
/* stylelint-disable-next-line selector-max-type */
.jp-HTMLSelect.jp-DefaultStyle select:hover,
.jp-HTMLSelect.jp-DefaultStyle select > option {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color0);
}

select {
  box-sizing: border-box;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-StatusBar-Widget {
  display: flex;
  align-items: center;
  background: var(--jp-layout-color2);
  min-height: var(--jp-statusbar-height);
  justify-content: space-between;
  padding: 0 10px;
}

.jp-StatusBar-Left {
  display: flex;
  align-items: center;
  flex-direction: row;
}

.jp-StatusBar-Middle {
  display: flex;
  align-items: center;
}

.jp-StatusBar-Right {
  display: flex;
  align-items: center;
  flex-direction: row-reverse;
}

.jp-StatusBar-Item {
  max-height: var(--jp-statusbar-height);
  margin: 0 2px;
  height: var(--jp-statusbar-height);
  white-space: nowrap;
  text-overflow: ellipsis;
  color: var(--jp-ui-font-color1);
  padding: 0 6px;
}

.jp-mod-highlighted:hover {
  background-color: var(--jp-layout-color3);
}

.jp-mod-clicked {
  background-color: var(--jp-brand-color1);
}

.jp-mod-clicked:hover {
  background-color: var(--jp-brand-color0);
}

.jp-mod-clicked .jp-StatusBar-TextItem {
  color: var(--jp-ui-inverse-font-color1);
}

.jp-StatusBar-HoverItem {
  box-shadow: '0px 4px 4px rgba(0, 0, 0, 0.25)';
}

.jp-StatusBar-TextItem {
  font-size: var(--jp-ui-font-size1);
  font-family: var(--jp-ui-font-family);
  line-height: 24px;
  color: var(--jp-ui-font-color1);
}

.jp-StatusBar-GroupItem {
  display: flex;
  align-items: center;
  flex-direction: row;
}

.jp-Statusbar-ProgressCircle svg {
  display: block;
  margin: 0 auto;
  width: 16px;
  height: 24px;
  align-self: normal;
}

.jp-Statusbar-ProgressCircle path {
  fill: var(--jp-inverse-layout-color3);
}

.jp-Statusbar-ProgressBar-progress-bar {
  height: 10px;
  width: 100px;
  border: solid 0.25px var(--jp-brand-color2);
  border-radius: 3px;
  overflow: hidden;
  align-self: center;
}

.jp-Statusbar-ProgressBar-progress-bar > div {
  background-color: var(--jp-brand-color2);
  background-image: linear-gradient(
    -45deg,
    rgba(255, 255, 255, 0.2) 25%,
    transparent 25%,
    transparent 50%,
    rgba(255, 255, 255, 0.2) 50%,
    rgba(255, 255, 255, 0.2) 75%,
    transparent 75%,
    transparent
  );
  background-size: 40px 40px;
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 14px;
  color: #fff;
  text-align: center;
  animation: jp-Statusbar-ExecutionTime-progress-bar 2s linear infinite;
}

.jp-Statusbar-ProgressBar-progress-bar p {
  color: var(--jp-ui-font-color1);
  font-family: var(--jp-ui-font-family);
  font-size: var(--jp-ui-font-size1);
  line-height: 10px;
  width: 100px;
}

@keyframes jp-Statusbar-ExecutionTime-progress-bar {
  0% {
    background-position: 0 0;
  }

  100% {
    background-position: 40px 40px;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-commandpalette-search-height: 28px;
}

/*-----------------------------------------------------------------------------
| Overall styles
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  padding-bottom: 0;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);

  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Modal variant
|----------------------------------------------------------------------------*/

.jp-ModalCommandPalette {
  position: absolute;
  z-index: 10000;
  top: 38px;
  left: 30%;
  margin: 0;
  padding: 4px;
  width: 40%;
  box-shadow: var(--jp-elevation-z4);
  border-radius: 4px;
  background: var(--jp-layout-color0);
}

.jp-ModalCommandPalette .lm-CommandPalette {
  max-height: 40vh;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-close-icon::after {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-header {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-item {
  margin-left: 4px;
  margin-right: 4px;
}

.jp-ModalCommandPalette
  .lm-CommandPalette
  .lm-CommandPalette-item.lm-mod-disabled {
  display: none;
}

/*-----------------------------------------------------------------------------
| Search
|----------------------------------------------------------------------------*/

.lm-CommandPalette-search {
  padding: 4px;
  background-color: var(--jp-layout-color1);
  z-index: 2;
}

.lm-CommandPalette-wrapper {
  overflow: overlay;
  padding: 0 9px;
  background-color: var(--jp-input-active-background);
  height: 30px;
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.lm-CommandPalette.lm-mod-focused .lm-CommandPalette-wrapper {
  box-shadow: inset 0 0 0 1px var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-SearchIconGroup {
  color: white;
  background-color: var(--jp-brand-color1);
  position: absolute;
  top: 4px;
  right: 4px;
  padding: 5px 5px 1px;
}

.jp-SearchIconGroup svg {
  height: 20px;
  width: 20px;
}

.jp-SearchIconGroup .jp-icon3[fill] {
  fill: var(--jp-layout-color0);
}

.lm-CommandPalette-input {
  background: transparent;
  width: calc(100% - 18px);
  float: left;
  border: none;
  outline: none;
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  line-height: var(--jp-private-commandpalette-search-height);
}

.lm-CommandPalette-input::-webkit-input-placeholder,
.lm-CommandPalette-input::-moz-placeholder,
.lm-CommandPalette-input:-ms-input-placeholder {
  color: var(--jp-ui-font-color2);
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Results
|----------------------------------------------------------------------------*/

.lm-CommandPalette-header:first-child {
  margin-top: 0;
}

.lm-CommandPalette-header {
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin-top: 8px;
  padding: 8px 0 8px 12px;
  text-transform: uppercase;
}

.lm-CommandPalette-header.lm-mod-active {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-header > mark {
  background-color: transparent;
  font-weight: bold;
  color: var(--jp-ui-font-color1);
}

.lm-CommandPalette-item {
  padding: 4px 12px 4px 4px;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  font-weight: 400;
  display: flex;
}

.lm-CommandPalette-item.lm-mod-disabled {
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item.lm-mod-active {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.lm-CommandPalette-item.lm-mod-active .lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-inverse-font-color0);
}

.lm-CommandPalette-item.lm-mod-active .jp-icon-selectable[fill] {
  fill: var(--jp-layout-color0);
}

.lm-CommandPalette-item.lm-mod-active:hover:not(.lm-mod-disabled) {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.lm-CommandPalette-item:hover:not(.lm-mod-active):not(.lm-mod-disabled) {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-itemContent {
  overflow: hidden;
}

.lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.lm-CommandPalette-item.lm-mod-disabled mark {
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item .lm-CommandPalette-itemIcon {
  margin: 0 4px 0 0;
  position: relative;
  width: 16px;
  top: 2px;
  flex: 0 0 auto;
}

.lm-CommandPalette-item.lm-mod-disabled .lm-CommandPalette-itemIcon {
  opacity: 0.6;
}

.lm-CommandPalette-item .lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemCaption {
  display: none;
}

.lm-CommandPalette-content {
  background-color: var(--jp-layout-color1);
}

.lm-CommandPalette-content:empty::after {
  content: 'No results';
  margin: auto;
  margin-top: 20px;
  width: 100px;
  display: block;
  font-size: var(--jp-ui-font-size2);
  font-family: var(--jp-ui-font-family);
  font-weight: lighter;
}

.lm-CommandPalette-emptyMessage {
  text-align: center;
  margin-top: 24px;
  line-height: 1.32;
  padding: 0 8px;
  color: var(--jp-content-font-color3);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Dialog {
  position: absolute;
  z-index: 10000;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  top: 0;
  left: 0;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-dialog-background);
}

.jp-Dialog-content {
  display: flex;
  flex-direction: column;
  margin-left: auto;
  margin-right: auto;
  background: var(--jp-layout-color1);
  padding: 24px 24px 12px;
  min-width: 300px;
  min-height: 150px;
  max-width: 1000px;
  max-height: 500px;
  box-sizing: border-box;
  box-shadow: var(--jp-elevation-z20);
  word-wrap: break-word;
  border-radius: var(--jp-border-radius);

  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color1);
  resize: both;
}

.jp-Dialog-content.jp-Dialog-content-small {
  max-width: 500px;
}

.jp-Dialog-button {
  overflow: visible;
}

button.jp-Dialog-button:focus {
  outline: 1px solid var(--jp-brand-color1);
  outline-offset: 4px;
  -moz-outline-radius: 0;
}

button.jp-Dialog-button:focus::-moz-focus-inner {
  border: 0;
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-accept:focus,
button.jp-Dialog-button.jp-mod-styled.jp-mod-warn:focus,
button.jp-Dialog-button.jp-mod-styled.jp-mod-reject:focus {
  outline-offset: 4px;
  -moz-outline-radius: 0;
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-accept:focus {
  outline: 1px solid var(--jp-accept-color-normal, var(--jp-brand-color1));
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-warn:focus {
  outline: 1px solid var(--jp-warn-color-normal, var(--jp-error-color1));
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-reject:focus {
  outline: 1px solid var(--jp-reject-color-normal, var(--md-grey-600));
}

button.jp-Dialog-close-button {
  padding: 0;
  height: 100%;
  min-width: unset;
  min-height: unset;
}

.jp-Dialog-header {
  display: flex;
  justify-content: space-between;
  flex: 0 0 auto;
  padding-bottom: 12px;
  font-size: var(--jp-ui-font-size3);
  font-weight: 400;
  color: var(--jp-ui-font-color1);
}

.jp-Dialog-body {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  font-size: var(--jp-ui-font-size1);
  background: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

.jp-Dialog-footer {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  align-items: center;
  flex: 0 0 auto;
  margin-left: -12px;
  margin-right: -12px;
  padding: 12px;
}

.jp-Dialog-checkbox {
  padding-right: 5px;
}

.jp-Dialog-checkbox > input:focus-visible {
  outline: 1px solid var(--jp-input-active-border-color);
  outline-offset: 1px;
}

.jp-Dialog-spacer {
  flex: 1 1 auto;
}

.jp-Dialog-title {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.jp-Dialog-body > .jp-select-wrapper {
  width: 100%;
}

.jp-Dialog-body > button {
  padding: 0 16px;
}

.jp-Dialog-body > label {
  line-height: 1.4;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-button.jp-mod-styled:not(:last-child) {
  margin-right: 12px;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-Input-Boolean-Dialog {
  flex-direction: row-reverse;
  align-items: end;
  width: 100%;
}

.jp-Input-Boolean-Dialog > label {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MainAreaWidget > :focus {
  outline: none;
}

.jp-MainAreaWidget .jp-MainAreaWidget-error {
  padding: 6px;
}

.jp-MainAreaWidget .jp-MainAreaWidget-error > pre {
  width: auto;
  padding: 10px;
  background: var(--jp-error-color3);
  border: var(--jp-border-width) solid var(--jp-error-color1);
  border-radius: var(--jp-border-radius);
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  white-space: pre-wrap;
  word-wrap: break-word;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/**
 * google-material-color v1.2.6
 * https://github.com/danlevan/google-material-color
 */
:root {
  --md-red-50: #ffebee;
  --md-red-100: #ffcdd2;
  --md-red-200: #ef9a9a;
  --md-red-300: #e57373;
  --md-red-400: #ef5350;
  --md-red-500: #f44336;
  --md-red-600: #e53935;
  --md-red-700: #d32f2f;
  --md-red-800: #c62828;
  --md-red-900: #b71c1c;
  --md-red-A100: #ff8a80;
  --md-red-A200: #ff5252;
  --md-red-A400: #ff1744;
  --md-red-A700: #d50000;
  --md-pink-50: #fce4ec;
  --md-pink-100: #f8bbd0;
  --md-pink-200: #f48fb1;
  --md-pink-300: #f06292;
  --md-pink-400: #ec407a;
  --md-pink-500: #e91e63;
  --md-pink-600: #d81b60;
  --md-pink-700: #c2185b;
  --md-pink-800: #ad1457;
  --md-pink-900: #880e4f;
  --md-pink-A100: #ff80ab;
  --md-pink-A200: #ff4081;
  --md-pink-A400: #f50057;
  --md-pink-A700: #c51162;
  --md-purple-50: #f3e5f5;
  --md-purple-100: #e1bee7;
  --md-purple-200: #ce93d8;
  --md-purple-300: #ba68c8;
  --md-purple-400: #ab47bc;
  --md-purple-500: #9c27b0;
  --md-purple-600: #8e24aa;
  --md-purple-700: #7b1fa2;
  --md-purple-800: #6a1b9a;
  --md-purple-900: #4a148c;
  --md-purple-A100: #ea80fc;
  --md-purple-A200: #e040fb;
  --md-purple-A400: #d500f9;
  --md-purple-A700: #a0f;
  --md-deep-purple-50: #ede7f6;
  --md-deep-purple-100: #d1c4e9;
  --md-deep-purple-200: #b39ddb;
  --md-deep-purple-300: #9575cd;
  --md-deep-purple-400: #7e57c2;
  --md-deep-purple-500: #673ab7;
  --md-deep-purple-600: #5e35b1;
  --md-deep-purple-700: #512da8;
  --md-deep-purple-800: #4527a0;
  --md-deep-purple-900: #311b92;
  --md-deep-purple-A100: #b388ff;
  --md-deep-purple-A200: #7c4dff;
  --md-deep-purple-A400: #651fff;
  --md-deep-purple-A700: #6200ea;
  --md-indigo-50: #e8eaf6;
  --md-indigo-100: #c5cae9;
  --md-indigo-200: #9fa8da;
  --md-indigo-300: #7986cb;
  --md-indigo-400: #5c6bc0;
  --md-indigo-500: #3f51b5;
  --md-indigo-600: #3949ab;
  --md-indigo-700: #303f9f;
  --md-indigo-800: #283593;
  --md-indigo-900: #1a237e;
  --md-indigo-A100: #8c9eff;
  --md-indigo-A200: #536dfe;
  --md-indigo-A400: #3d5afe;
  --md-indigo-A700: #304ffe;
  --md-blue-50: #e3f2fd;
  --md-blue-100: #bbdefb;
  --md-blue-200: #90caf9;
  --md-blue-300: #64b5f6;
  --md-blue-400: #42a5f5;
  --md-blue-500: #2196f3;
  --md-blue-600: #1e88e5;
  --md-blue-700: #1976d2;
  --md-blue-800: #1565c0;
  --md-blue-900: #0d47a1;
  --md-blue-A100: #82b1ff;
  --md-blue-A200: #448aff;
  --md-blue-A400: #2979ff;
  --md-blue-A700: #2962ff;
  --md-light-blue-50: #e1f5fe;
  --md-light-blue-100: #b3e5fc;
  --md-light-blue-200: #81d4fa;
  --md-light-blue-300: #4fc3f7;
  --md-light-blue-400: #29b6f6;
  --md-light-blue-500: #03a9f4;
  --md-light-blue-600: #039be5;
  --md-light-blue-700: #0288d1;
  --md-light-blue-800: #0277bd;
  --md-light-blue-900: #01579b;
  --md-light-blue-A100: #80d8ff;
  --md-light-blue-A200: #40c4ff;
  --md-light-blue-A400: #00b0ff;
  --md-light-blue-A700: #0091ea;
  --md-cyan-50: #e0f7fa;
  --md-cyan-100: #b2ebf2;
  --md-cyan-200: #80deea;
  --md-cyan-300: #4dd0e1;
  --md-cyan-400: #26c6da;
  --md-cyan-500: #00bcd4;
  --md-cyan-600: #00acc1;
  --md-cyan-700: #0097a7;
  --md-cyan-800: #00838f;
  --md-cyan-900: #006064;
  --md-cyan-A100: #84ffff;
  --md-cyan-A200: #18ffff;
  --md-cyan-A400: #00e5ff;
  --md-cyan-A700: #00b8d4;
  --md-teal-50: #e0f2f1;
  --md-teal-100: #b2dfdb;
  --md-teal-200: #80cbc4;
  --md-teal-300: #4db6ac;
  --md-teal-400: #26a69a;
  --md-teal-500: #009688;
  --md-teal-600: #00897b;
  --md-teal-700: #00796b;
  --md-teal-800: #00695c;
  --md-teal-900: #004d40;
  --md-teal-A100: #a7ffeb;
  --md-teal-A200: #64ffda;
  --md-teal-A400: #1de9b6;
  --md-teal-A700: #00bfa5;
  --md-green-50: #e8f5e9;
  --md-green-100: #c8e6c9;
  --md-green-200: #a5d6a7;
  --md-green-300: #81c784;
  --md-green-400: #66bb6a;
  --md-green-500: #4caf50;
  --md-green-600: #43a047;
  --md-green-700: #388e3c;
  --md-green-800: #2e7d32;
  --md-green-900: #1b5e20;
  --md-green-A100: #b9f6ca;
  --md-green-A200: #69f0ae;
  --md-green-A400: #00e676;
  --md-green-A700: #00c853;
  --md-light-green-50: #f1f8e9;
  --md-light-green-100: #dcedc8;
  --md-light-green-200: #c5e1a5;
  --md-light-green-300: #aed581;
  --md-light-green-400: #9ccc65;
  --md-light-green-500: #8bc34a;
  --md-light-green-600: #7cb342;
  --md-light-green-700: #689f38;
  --md-light-green-800: #558b2f;
  --md-light-green-900: #33691e;
  --md-light-green-A100: #ccff90;
  --md-light-green-A200: #b2ff59;
  --md-light-green-A400: #76ff03;
  --md-light-green-A700: #64dd17;
  --md-lime-50: #f9fbe7;
  --md-lime-100: #f0f4c3;
  --md-lime-200: #e6ee9c;
  --md-lime-300: #dce775;
  --md-lime-400: #d4e157;
  --md-lime-500: #cddc39;
  --md-lime-600: #c0ca33;
  --md-lime-700: #afb42b;
  --md-lime-800: #9e9d24;
  --md-lime-900: #827717;
  --md-lime-A100: #f4ff81;
  --md-lime-A200: #eeff41;
  --md-lime-A400: #c6ff00;
  --md-lime-A700: #aeea00;
  --md-yellow-50: #fffde7;
  --md-yellow-100: #fff9c4;
  --md-yellow-200: #fff59d;
  --md-yellow-300: #fff176;
  --md-yellow-400: #ffee58;
  --md-yellow-500: #ffeb3b;
  --md-yellow-600: #fdd835;
  --md-yellow-700: #fbc02d;
  --md-yellow-800: #f9a825;
  --md-yellow-900: #f57f17;
  --md-yellow-A100: #ffff8d;
  --md-yellow-A200: #ff0;
  --md-yellow-A400: #ffea00;
  --md-yellow-A700: #ffd600;
  --md-amber-50: #fff8e1;
  --md-amber-100: #ffecb3;
  --md-amber-200: #ffe082;
  --md-amber-300: #ffd54f;
  --md-amber-400: #ffca28;
  --md-amber-500: #ffc107;
  --md-amber-600: #ffb300;
  --md-amber-700: #ffa000;
  --md-amber-800: #ff8f00;
  --md-amber-900: #ff6f00;
  --md-amber-A100: #ffe57f;
  --md-amber-A200: #ffd740;
  --md-amber-A400: #ffc400;
  --md-amber-A700: #ffab00;
  --md-orange-50: #fff3e0;
  --md-orange-100: #ffe0b2;
  --md-orange-200: #ffcc80;
  --md-orange-300: #ffb74d;
  --md-orange-400: #ffa726;
  --md-orange-500: #ff9800;
  --md-orange-600: #fb8c00;
  --md-orange-700: #f57c00;
  --md-orange-800: #ef6c00;
  --md-orange-900: #e65100;
  --md-orange-A100: #ffd180;
  --md-orange-A200: #ffab40;
  --md-orange-A400: #ff9100;
  --md-orange-A700: #ff6d00;
  --md-deep-orange-50: #fbe9e7;
  --md-deep-orange-100: #ffccbc;
  --md-deep-orange-200: #ffab91;
  --md-deep-orange-300: #ff8a65;
  --md-deep-orange-400: #ff7043;
  --md-deep-orange-500: #ff5722;
  --md-deep-orange-600: #f4511e;
  --md-deep-orange-700: #e64a19;
  --md-deep-orange-800: #d84315;
  --md-deep-orange-900: #bf360c;
  --md-deep-orange-A100: #ff9e80;
  --md-deep-orange-A200: #ff6e40;
  --md-deep-orange-A400: #ff3d00;
  --md-deep-orange-A700: #dd2c00;
  --md-brown-50: #efebe9;
  --md-brown-100: #d7ccc8;
  --md-brown-200: #bcaaa4;
  --md-brown-300: #a1887f;
  --md-brown-400: #8d6e63;
  --md-brown-500: #795548;
  --md-brown-600: #6d4c41;
  --md-brown-700: #5d4037;
  --md-brown-800: #4e342e;
  --md-brown-900: #3e2723;
  --md-grey-50: #fafafa;
  --md-grey-100: #f5f5f5;
  --md-grey-200: #eee;
  --md-grey-300: #e0e0e0;
  --md-grey-400: #bdbdbd;
  --md-grey-500: #9e9e9e;
  --md-grey-600: #757575;
  --md-grey-700: #616161;
  --md-grey-800: #424242;
  --md-grey-900: #212121;
  --md-blue-grey-50: #eceff1;
  --md-blue-grey-100: #cfd8dc;
  --md-blue-grey-200: #b0bec5;
  --md-blue-grey-300: #90a4ae;
  --md-blue-grey-400: #78909c;
  --md-blue-grey-500: #607d8b;
  --md-blue-grey-600: #546e7a;
  --md-blue-grey-700: #455a64;
  --md-blue-grey-800: #37474f;
  --md-blue-grey-900: #263238;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| RenderedText
|----------------------------------------------------------------------------*/

:root {
  /* This is the padding value to fill the gaps between lines containing spans with background color. */
  --jp-private-code-span-padding: calc(
    (var(--jp-code-line-height) - 1) * var(--jp-code-font-size) / 2
  );
}

.jp-RenderedText {
  text-align: left;
  padding-left: var(--jp-code-padding);
  line-height: var(--jp-code-line-height);
  font-family: var(--jp-code-font-family);
}

.jp-RenderedText pre,
.jp-RenderedJavaScript pre,
.jp-RenderedHTMLCommon pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
  border: none;
  margin: 0;
  padding: 0;
}

.jp-RenderedText pre a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedText pre a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedText pre a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* console foregrounds and backgrounds */
.jp-RenderedText pre .ansi-black-fg {
  color: #3e424d;
}

.jp-RenderedText pre .ansi-red-fg {
  color: #e75c58;
}

.jp-RenderedText pre .ansi-green-fg {
  color: #00a250;
}

.jp-RenderedText pre .ansi-yellow-fg {
  color: #ddb62b;
}

.jp-RenderedText pre .ansi-blue-fg {
  color: #208ffb;
}

.jp-RenderedText pre .ansi-magenta-fg {
  color: #d160c4;
}

.jp-RenderedText pre .ansi-cyan-fg {
  color: #60c6c8;
}

.jp-RenderedText pre .ansi-white-fg {
  color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-bg {
  background-color: #3e424d;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-red-bg {
  background-color: #e75c58;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-green-bg {
  background-color: #00a250;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-yellow-bg {
  background-color: #ddb62b;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-blue-bg {
  background-color: #208ffb;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-magenta-bg {
  background-color: #d160c4;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-cyan-bg {
  background-color: #60c6c8;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-white-bg {
  background-color: #c5c1b4;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-black-intense-fg {
  color: #282c36;
}

.jp-RenderedText pre .ansi-red-intense-fg {
  color: #b22b31;
}

.jp-RenderedText pre .ansi-green-intense-fg {
  color: #007427;
}

.jp-RenderedText pre .ansi-yellow-intense-fg {
  color: #b27d12;
}

.jp-RenderedText pre .ansi-blue-intense-fg {
  color: #0065ca;
}

.jp-RenderedText pre .ansi-magenta-intense-fg {
  color: #a03196;
}

.jp-RenderedText pre .ansi-cyan-intense-fg {
  color: #258f8f;
}

.jp-RenderedText pre .ansi-white-intense-fg {
  color: #a1a6b2;
}

.jp-RenderedText pre .ansi-black-intense-bg {
  background-color: #282c36;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-red-intense-bg {
  background-color: #b22b31;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-green-intense-bg {
  background-color: #007427;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-yellow-intense-bg {
  background-color: #b27d12;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-blue-intense-bg {
  background-color: #0065ca;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-magenta-intense-bg {
  background-color: #a03196;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-cyan-intense-bg {
  background-color: #258f8f;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-white-intense-bg {
  background-color: #a1a6b2;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-default-inverse-fg {
  color: var(--jp-ui-inverse-font-color0);
}

.jp-RenderedText pre .ansi-default-inverse-bg {
  background-color: var(--jp-inverse-layout-color0);
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-bold {
  font-weight: bold;
}

.jp-RenderedText pre .ansi-underline {
  text-decoration: underline;
}

.jp-RenderedText[data-mime-type='application/vnd.jupyter.stderr'] {
  background: var(--jp-rendermime-error-background);
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| RenderedLatex
|----------------------------------------------------------------------------*/

.jp-RenderedLatex {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
}

/* Left-justify outputs.*/
.jp-OutputArea-output.jp-RenderedLatex {
  padding: var(--jp-code-padding);
  text-align: left;
}

/*-----------------------------------------------------------------------------
| RenderedHTML
|----------------------------------------------------------------------------*/

.jp-RenderedHTMLCommon {
  color: var(--jp-content-font-color1);
  font-family: var(--jp-content-font-family);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);

  /* Give a bit more R padding on Markdown text to keep line lengths reasonable */
  padding-right: 20px;
}

.jp-RenderedHTMLCommon em {
  font-style: italic;
}

.jp-RenderedHTMLCommon strong {
  font-weight: bold;
}

.jp-RenderedHTMLCommon u {
  text-decoration: underline;
}

.jp-RenderedHTMLCommon a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* Headings */

.jp-RenderedHTMLCommon h1,
.jp-RenderedHTMLCommon h2,
.jp-RenderedHTMLCommon h3,
.jp-RenderedHTMLCommon h4,
.jp-RenderedHTMLCommon h5,
.jp-RenderedHTMLCommon h6 {
  line-height: var(--jp-content-heading-line-height);
  font-weight: var(--jp-content-heading-font-weight);
  font-style: normal;
  margin: var(--jp-content-heading-margin-top) 0
    var(--jp-content-heading-margin-bottom) 0;
}

.jp-RenderedHTMLCommon h1:first-child,
.jp-RenderedHTMLCommon h2:first-child,
.jp-RenderedHTMLCommon h3:first-child,
.jp-RenderedHTMLCommon h4:first-child,
.jp-RenderedHTMLCommon h5:first-child,
.jp-RenderedHTMLCommon h6:first-child {
  margin-top: calc(0.5 * var(--jp-content-heading-margin-top));
}

.jp-RenderedHTMLCommon h1:last-child,
.jp-RenderedHTMLCommon h2:last-child,
.jp-RenderedHTMLCommon h3:last-child,
.jp-RenderedHTMLCommon h4:last-child,
.jp-RenderedHTMLCommon h5:last-child,
.jp-RenderedHTMLCommon h6:last-child {
  margin-bottom: calc(0.5 * var(--jp-content-heading-margin-bottom));
}

.jp-RenderedHTMLCommon h1 {
  font-size: var(--jp-content-font-size5);
}

.jp-RenderedHTMLCommon h2 {
  font-size: var(--jp-content-font-size4);
}

.jp-RenderedHTMLCommon h3 {
  font-size: var(--jp-content-font-size3);
}

.jp-RenderedHTMLCommon h4 {
  font-size: var(--jp-content-font-size2);
}

.jp-RenderedHTMLCommon h5 {
  font-size: var(--jp-content-font-size1);
}

.jp-RenderedHTMLCommon h6 {
  font-size: var(--jp-content-font-size0);
}

/* Lists */

/* stylelint-disable selector-max-type, selector-max-compound-selectors */

.jp-RenderedHTMLCommon ul:not(.list-inline),
.jp-RenderedHTMLCommon ol:not(.list-inline) {
  padding-left: 2em;
}

.jp-RenderedHTMLCommon ul {
  list-style: disc;
}

.jp-RenderedHTMLCommon ul ul {
  list-style: square;
}

.jp-RenderedHTMLCommon ul ul ul {
  list-style: circle;
}

.jp-RenderedHTMLCommon ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol ol {
  list-style: upper-alpha;
}

.jp-RenderedHTMLCommon ol ol ol {
  list-style: lower-alpha;
}

.jp-RenderedHTMLCommon ol ol ol ol {
  list-style: lower-roman;
}

.jp-RenderedHTMLCommon ol ol ol ol ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol,
.jp-RenderedHTMLCommon ul {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon ul ul,
.jp-RenderedHTMLCommon ul ol,
.jp-RenderedHTMLCommon ol ul,
.jp-RenderedHTMLCommon ol ol {
  margin-bottom: 0;
}

/* stylelint-enable selector-max-type, selector-max-compound-selectors */

.jp-RenderedHTMLCommon hr {
  color: var(--jp-border-color2);
  background-color: var(--jp-border-color1);
  margin-top: 1em;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon > pre {
  margin: 1.5em 2em;
}

.jp-RenderedHTMLCommon pre,
.jp-RenderedHTMLCommon code {
  border: 0;
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  line-height: var(--jp-code-line-height);
  padding: 0;
  white-space: pre-wrap;
}

.jp-RenderedHTMLCommon :not(pre) > code {
  background-color: var(--jp-layout-color2);
  padding: 1px 5px;
}

/* Tables */

.jp-RenderedHTMLCommon table {
  border-collapse: collapse;
  border-spacing: 0;
  border: none;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  table-layout: fixed;
  margin-left: auto;
  margin-bottom: 1em;
  margin-right: auto;
}

.jp-RenderedHTMLCommon thead {
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  vertical-align: bottom;
}

.jp-RenderedHTMLCommon td,
.jp-RenderedHTMLCommon th,
.jp-RenderedHTMLCommon tr {
  vertical-align: middle;
  padding: 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}

.jp-RenderedMarkdown.jp-RenderedHTMLCommon td,
.jp-RenderedMarkdown.jp-RenderedHTMLCommon th {
  max-width: none;
}

:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon td,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon th,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon tr {
  text-align: right;
}

.jp-RenderedHTMLCommon th {
  font-weight: bold;
}

.jp-RenderedHTMLCommon tbody tr:nth-child(odd) {
  background: var(--jp-layout-color0);
}

.jp-RenderedHTMLCommon tbody tr:nth-child(even) {
  background: var(--jp-rendermime-table-row-background);
}

.jp-RenderedHTMLCommon tbody tr:hover {
  background: var(--jp-rendermime-table-row-hover-background);
}

.jp-RenderedHTMLCommon p {
  text-align: left;
  margin: 0;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon img {
  -moz-force-broken-image-icon: 1;
}

/* Restrict to direct children as other images could be nested in other content. */
.jp-RenderedHTMLCommon > img {
  display: block;
  margin-left: 0;
  margin-right: 0;
  margin-bottom: 1em;
}

/* Change color behind transparent images if they need it... */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-light-background {
  background-color: var(--jp-inverse-layout-color1);
}

[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-dark-background {
  background-color: var(--jp-inverse-layout-color1);
}

.jp-RenderedHTMLCommon img,
.jp-RenderedImage img,
.jp-RenderedHTMLCommon svg,
.jp-RenderedSVG svg {
  max-width: 100%;
  height: auto;
}

.jp-RenderedHTMLCommon img.jp-mod-unconfined,
.jp-RenderedImage img.jp-mod-unconfined,
.jp-RenderedHTMLCommon svg.jp-mod-unconfined,
.jp-RenderedSVG svg.jp-mod-unconfined {
  max-width: none;
}

.jp-RenderedHTMLCommon .alert {
  padding: var(--jp-notebook-padding);
  border: var(--jp-border-width) solid transparent;
  border-radius: var(--jp-border-radius);
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon .alert-info {
  color: var(--jp-info-color0);
  background-color: var(--jp-info-color3);
  border-color: var(--jp-info-color2);
}

.jp-RenderedHTMLCommon .alert-info hr {
  border-color: var(--jp-info-color3);
}

.jp-RenderedHTMLCommon .alert-info > p:last-child,
.jp-RenderedHTMLCommon .alert-info > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-warning {
  color: var(--jp-warn-color0);
  background-color: var(--jp-warn-color3);
  border-color: var(--jp-warn-color2);
}

.jp-RenderedHTMLCommon .alert-warning hr {
  border-color: var(--jp-warn-color3);
}

.jp-RenderedHTMLCommon .alert-warning > p:last-child,
.jp-RenderedHTMLCommon .alert-warning > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-success {
  color: var(--jp-success-color0);
  background-color: var(--jp-success-color3);
  border-color: var(--jp-success-color2);
}

.jp-RenderedHTMLCommon .alert-success hr {
  border-color: var(--jp-success-color3);
}

.jp-RenderedHTMLCommon .alert-success > p:last-child,
.jp-RenderedHTMLCommon .alert-success > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-danger {
  color: var(--jp-error-color0);
  background-color: var(--jp-error-color3);
  border-color: var(--jp-error-color2);
}

.jp-RenderedHTMLCommon .alert-danger hr {
  border-color: var(--jp-error-color3);
}

.jp-RenderedHTMLCommon .alert-danger > p:last-child,
.jp-RenderedHTMLCommon .alert-danger > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon blockquote {
  margin: 1em 2em;
  padding: 0 1em;
  border-left: 5px solid var(--jp-border-color2);
}

a.jp-InternalAnchorLink {
  visibility: hidden;
  margin-left: 8px;
  color: var(--md-blue-800);
}

h1:hover .jp-InternalAnchorLink,
h2:hover .jp-InternalAnchorLink,
h3:hover .jp-InternalAnchorLink,
h4:hover .jp-InternalAnchorLink,
h5:hover .jp-InternalAnchorLink,
h6:hover .jp-InternalAnchorLink {
  visibility: visible;
}

.jp-RenderedHTMLCommon kbd {
  background-color: var(--jp-rendermime-table-row-background);
  border: 1px solid var(--jp-border-color0);
  border-bottom-color: var(--jp-border-color2);
  border-radius: 3px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
  display: inline-block;
  font-size: var(--jp-ui-font-size0);
  line-height: 1em;
  padding: 0.2em 0.5em;
}

/* Most direct children of .jp-RenderedHTMLCommon have a margin-bottom of 1.0.
 * At the bottom of cells this is a bit too much as there is also spacing
 * between cells. Going all the way to 0 gets too tight between markdown and
 * code cells.
 */
.jp-RenderedHTMLCommon > *:last-child {
  margin-bottom: 0.5em;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-cursor-backdrop {
  position: fixed;
  width: 200px;
  height: 200px;
  margin-top: -100px;
  margin-left: -100px;
  will-change: transform;
  z-index: 100;
}

.lm-mod-drag-image {
  will-change: transform;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-lineFormSearch {
  padding: 4px 12px;
  background-color: var(--jp-layout-color2);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
  font-size: var(--jp-ui-font-size1);
}

.jp-lineFormCaption {
  font-size: var(--jp-ui-font-size0);
  line-height: var(--jp-ui-font-size1);
  margin-top: 4px;
  color: var(--jp-ui-font-color0);
}

.jp-baseLineForm {
  border: none;
  border-radius: 0;
  position: absolute;
  background-size: 16px;
  background-repeat: no-repeat;
  background-position: center;
  outline: none;
}

.jp-lineFormButtonContainer {
  top: 4px;
  right: 8px;
  height: 24px;
  padding: 0 12px;
  width: 12px;
}

.jp-lineFormButtonIcon {
  top: 0;
  right: 0;
  background-color: var(--jp-brand-color1);
  height: 100%;
  width: 100%;
  box-sizing: border-box;
  padding: 4px 6px;
}

.jp-lineFormButton {
  top: 0;
  right: 0;
  background-color: transparent;
  height: 100%;
  width: 100%;
  box-sizing: border-box;
}

.jp-lineFormWrapper {
  overflow: hidden;
  padding: 0 8px;
  border: 1px solid var(--jp-border-color0);
  background-color: var(--jp-input-active-background);
  height: 22px;
}

.jp-lineFormWrapperFocusWithin {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-lineFormInput {
  background: transparent;
  width: 200px;
  height: 100%;
  border: none;
  outline: none;
  color: var(--jp-ui-font-color0);
  line-height: 28px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-JSONEditor {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.jp-JSONEditor-host {
  flex: 1 1 auto;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0;
  background: var(--jp-layout-color0);
  min-height: 50px;
  padding: 1px;
}

.jp-JSONEditor.jp-mod-error .jp-JSONEditor-host {
  border-color: red;
  outline-color: red;
}

.jp-JSONEditor-header {
  display: flex;
  flex: 1 0 auto;
  padding: 0 0 0 12px;
}

.jp-JSONEditor-header label {
  flex: 0 0 auto;
}

.jp-JSONEditor-commitButton {
  height: 16px;
  width: 16px;
  background-size: 18px;
  background-repeat: no-repeat;
  background-position: center;
}

.jp-JSONEditor-host.jp-mod-focused {
  background-color: var(--jp-input-active-background);
  border: 1px solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

.jp-Editor.jp-mod-dropTarget {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/
.jp-DocumentSearch-input {
  border: none;
  outline: none;
  color: var(--jp-ui-font-color0);
  font-size: var(--jp-ui-font-size1);
  background-color: var(--jp-layout-color0);
  font-family: var(--jp-ui-font-family);
  padding: 2px 1px;
  resize: none;
}

.jp-DocumentSearch-overlay {
  position: absolute;
  background-color: var(--jp-toolbar-background);
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  border-left: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  top: 0;
  right: 0;
  z-index: 7;
  min-width: 405px;
  padding: 2px;
  font-size: var(--jp-ui-font-size1);

  --jp-private-document-search-button-height: 20px;
}

.jp-DocumentSearch-overlay button {
  background-color: var(--jp-toolbar-background);
  outline: 0;
}

.jp-DocumentSearch-overlay button:hover {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-overlay button:active {
  background-color: var(--jp-layout-color3);
}

.jp-DocumentSearch-overlay-row {
  display: flex;
  align-items: center;
  margin-bottom: 2px;
}

.jp-DocumentSearch-button-content {
  display: inline-block;
  cursor: pointer;
  box-sizing: border-box;
  width: 100%;
  height: 100%;
}

.jp-DocumentSearch-button-content svg {
  width: 100%;
  height: 100%;
}

.jp-DocumentSearch-input-wrapper {
  border: var(--jp-border-width) solid var(--jp-border-color0);
  display: flex;
  background-color: var(--jp-layout-color0);
  margin: 2px;
}

.jp-DocumentSearch-input-wrapper:focus-within {
  border-color: var(--jp-cell-editor-active-border-color);
}

.jp-DocumentSearch-toggle-wrapper,
.jp-DocumentSearch-button-wrapper {
  all: initial;
  overflow: hidden;
  display: inline-block;
  border: none;
  box-sizing: border-box;
}

.jp-DocumentSearch-toggle-wrapper {
  width: 14px;
  height: 14px;
}

.jp-DocumentSearch-button-wrapper {
  width: var(--jp-private-document-search-button-height);
  height: var(--jp-private-document-search-button-height);
}

.jp-DocumentSearch-toggle-wrapper:focus,
.jp-DocumentSearch-button-wrapper:focus {
  outline: var(--jp-border-width) solid
    var(--jp-cell-editor-active-border-color);
  outline-offset: -1px;
}

.jp-DocumentSearch-toggle-wrapper,
.jp-DocumentSearch-button-wrapper,
.jp-DocumentSearch-button-content:focus {
  outline: none;
}

.jp-DocumentSearch-toggle-placeholder {
  width: 5px;
}

.jp-DocumentSearch-input-button::before {
  display: block;
  padding-top: 100%;
}

.jp-DocumentSearch-input-button-off {
  opacity: var(--jp-search-toggle-off-opacity);
}

.jp-DocumentSearch-input-button-off:hover {
  opacity: var(--jp-search-toggle-hover-opacity);
}

.jp-DocumentSearch-input-button-on {
  opacity: var(--jp-search-toggle-on-opacity);
}

.jp-DocumentSearch-index-counter {
  padding-left: 10px;
  padding-right: 10px;
  user-select: none;
  min-width: 35px;
  display: inline-block;
}

.jp-DocumentSearch-up-down-wrapper {
  display: inline-block;
  padding-right: 2px;
  margin-left: auto;
  white-space: nowrap;
}

.jp-DocumentSearch-spacer {
  margin-left: auto;
}

.jp-DocumentSearch-up-down-wrapper button {
  outline: 0;
  border: none;
  width: var(--jp-private-document-search-button-height);
  height: var(--jp-private-document-search-button-height);
  vertical-align: middle;
  margin: 1px 5px 2px;
}

.jp-DocumentSearch-up-down-button:hover {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-up-down-button:active {
  background-color: var(--jp-layout-color3);
}

.jp-DocumentSearch-filter-button {
  border-radius: var(--jp-border-radius);
}

.jp-DocumentSearch-filter-button:hover {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-filter-button-enabled {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-filter-button-enabled:hover {
  background-color: var(--jp-layout-color3);
}

.jp-DocumentSearch-search-options {
  padding: 0 8px;
  margin-left: 3px;
  width: 100%;
  display: grid;
  justify-content: start;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  justify-items: stretch;
}

.jp-DocumentSearch-search-filter-disabled {
  color: var(--jp-ui-font-color2);
}

.jp-DocumentSearch-search-filter {
  display: flex;
  align-items: center;
  user-select: none;
}

.jp-DocumentSearch-regex-error {
  color: var(--jp-error-color0);
}

.jp-DocumentSearch-replace-button-wrapper {
  overflow: hidden;
  display: inline-block;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color0);
  margin: auto 2px;
  padding: 1px 4px;
  height: calc(var(--jp-private-document-search-button-height) + 2px);
}

.jp-DocumentSearch-replace-button-wrapper:focus {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
}

.jp-DocumentSearch-replace-button {
  display: inline-block;
  text-align: center;
  cursor: pointer;
  box-sizing: border-box;
  color: var(--jp-ui-font-color1);

  /* height - 2 * (padding of wrapper) */
  line-height: calc(var(--jp-private-document-search-button-height) - 2px);
  width: 100%;
  height: 100%;
}

.jp-DocumentSearch-replace-button:focus {
  outline: none;
}

.jp-DocumentSearch-replace-wrapper-class {
  margin-left: 14px;
  display: flex;
}

.jp-DocumentSearch-replace-toggle {
  border: none;
  background-color: var(--jp-toolbar-background);
  border-radius: var(--jp-border-radius);
}

.jp-DocumentSearch-replace-toggle:hover {
  background-color: var(--jp-layout-color2);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.cm-editor {
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  border: 0;
  border-radius: 0;
  height: auto;

  /* Changed to auto to autogrow */
}

.cm-editor pre {
  padding: 0 var(--jp-code-padding);
}

.jp-CodeMirrorEditor[data-type='inline'] .cm-dialog {
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

.jp-CodeMirrorEditor {
  cursor: text;
}

/* When zoomed out 67% and 33% on a screen of 1440 width x 900 height */
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .jp-CodeMirrorEditor[data-type='inline'] .cm-cursor {
    border-left: var(--jp-code-cursor-width1) solid
      var(--jp-editor-cursor-color);
  }
}

/* When zoomed out less than 33% */
@media screen and (min-width: 4320px) {
  .jp-CodeMirrorEditor[data-type='inline'] .cm-cursor {
    border-left: var(--jp-code-cursor-width2) solid
      var(--jp-editor-cursor-color);
  }
}

.cm-editor.jp-mod-readOnly .cm-cursor {
  display: none;
}

.jp-CollaboratorCursor {
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: none;
  border-bottom: 3px solid;
  background-clip: content-box;
  margin-left: -5px;
  margin-right: -5px;
}

.cm-searching,
.cm-searching span {
  /* `.cm-searching span`: we need to override syntax highlighting */
  background-color: var(--jp-search-unselected-match-background-color);
  color: var(--jp-search-unselected-match-color);
}

.cm-searching::selection,
.cm-searching span::selection {
  background-color: var(--jp-search-unselected-match-background-color);
  color: var(--jp-search-unselected-match-color);
}

.jp-current-match > .cm-searching,
.jp-current-match > .cm-searching span,
.cm-searching > .jp-current-match,
.cm-searching > .jp-current-match span {
  background-color: var(--jp-search-selected-match-background-color);
  color: var(--jp-search-selected-match-color);
}

.jp-current-match > .cm-searching::selection,
.cm-searching > .jp-current-match::selection,
.jp-current-match > .cm-searching span::selection {
  background-color: var(--jp-search-selected-match-background-color);
  color: var(--jp-search-selected-match-color);
}

.cm-trailingspace {
  background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAFCAYAAAB4ka1VAAAAsElEQVQIHQGlAFr/AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA7+r3zKmT0/+pk9P/7+r3zAAAAAAAAAAABAAAAAAAAAAA6OPzM+/q9wAAAAAA6OPzMwAAAAAAAAAAAgAAAAAAAAAAGR8NiRQaCgAZIA0AGR8NiQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQyoYJ/SY80UAAAAASUVORK5CYII=);
  background-position: center left;
  background-repeat: repeat-x;
}

.jp-CollaboratorCursor-hover {
  position: absolute;
  z-index: 1;
  transform: translateX(-50%);
  color: white;
  border-radius: 3px;
  padding-left: 4px;
  padding-right: 4px;
  padding-top: 1px;
  padding-bottom: 1px;
  text-align: center;
  font-size: var(--jp-ui-font-size1);
  white-space: nowrap;
}

.jp-CodeMirror-ruler {
  border-left: 1px dashed var(--jp-border-color2);
}

/* Styles for shared cursors (remote cursor locations and selected ranges) */
.jp-CodeMirrorEditor .cm-ySelectionCaret {
  position: relative;
  border-left: 1px solid black;
  margin-left: -1px;
  margin-right: -1px;
  box-sizing: border-box;
}

.jp-CodeMirrorEditor .cm-ySelectionCaret > .cm-ySelectionInfo {
  white-space: nowrap;
  position: absolute;
  top: -1.15em;
  padding-bottom: 0.05em;
  left: -1px;
  font-size: 0.95em;
  font-family: var(--jp-ui-font-family);
  font-weight: bold;
  line-height: normal;
  user-select: none;
  color: white;
  padding-left: 2px;
  padding-right: 2px;
  z-index: 101;
  transition: opacity 0.3s ease-in-out;
}

.jp-CodeMirrorEditor .cm-ySelectionInfo {
  transition-delay: 0.7s;
  opacity: 0;
}

.jp-CodeMirrorEditor .cm-ySelectionCaret:hover > .cm-ySelectionInfo {
  opacity: 1;
  transition-delay: 0s;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MimeDocument {
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-filebrowser-button-height: 28px;
  --jp-private-filebrowser-button-width: 48px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FileBrowser .jp-SidePanel-content {
  display: flex;
  flex-direction: column;
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  flex-wrap: wrap;
  row-gap: 12px;
  border-bottom: none;
  height: auto;
  margin: 8px 12px 0;
  box-shadow: none;
  padding: 0;
  justify-content: flex-start;
}

.jp-FileBrowser-Panel {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
}

.jp-BreadCrumbs {
  flex: 0 0 auto;
  margin: 8px 12px;
}

.jp-BreadCrumbs-item {
  margin: 0 2px;
  padding: 0 2px;
  border-radius: var(--jp-border-radius);
  cursor: pointer;
}

.jp-BreadCrumbs-item:hover {
  background-color: var(--jp-layout-color2);
}

.jp-BreadCrumbs-item:first-child {
  margin-left: 0;
}

.jp-BreadCrumbs-item.jp-mod-dropTarget {
  background-color: var(--jp-brand-color2);
  opacity: 0.7;
}

/*-----------------------------------------------------------------------------
| Buttons
|----------------------------------------------------------------------------*/

.jp-FileBrowser-toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  padding-left: 0;
  padding-right: 2px;
  align-items: center;
  height: unset;
}

.jp-FileBrowser-toolbar > .jp-Toolbar-item .jp-ToolbarButtonComponent {
  width: 40px;
}

/*-----------------------------------------------------------------------------
| Other styles
|----------------------------------------------------------------------------*/

.jp-FileDialog.jp-mod-conflict input {
  color: var(--jp-error-color1);
}

.jp-FileDialog .jp-new-name-title {
  margin-top: 12px;
}

.jp-LastModified-hidden {
  display: none;
}

.jp-FileSize-hidden {
  display: none;
}

.jp-FileBrowser .lm-AccordionPanel > h3:first-child {
  display: none;
}

/*-----------------------------------------------------------------------------
| DirListing
|----------------------------------------------------------------------------*/

.jp-DirListing {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  outline: 0;
}

.jp-DirListing-header {
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  align-items: center;
  overflow: hidden;
  border-top: var(--jp-border-width) solid var(--jp-border-color2);
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
}

.jp-DirListing-headerItem {
  padding: 4px 12px 2px;
  font-weight: 500;
}

.jp-DirListing-headerItem:hover {
  background: var(--jp-layout-color2);
}

.jp-DirListing-headerItem.jp-id-name {
  flex: 1 0 84px;
}

.jp-DirListing-headerItem.jp-id-modified {
  flex: 0 0 112px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-DirListing-headerItem.jp-id-filesize {
  flex: 0 0 75px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-id-narrow {
  display: none;
  flex: 0 0 5px;
  padding: 4px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
  color: var(--jp-border-color2);
}

.jp-DirListing-narrow .jp-id-narrow {
  display: block;
}

.jp-DirListing-narrow .jp-id-modified,
.jp-DirListing-narrow .jp-DirListing-itemModified {
  display: none;
}

.jp-DirListing-headerItem.jp-mod-selected {
  font-weight: 600;
}

/* increase specificity to override bundled default */
.jp-DirListing-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

.jp-DirListing-content mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.jp-DirListing-content .jp-DirListing-item.jp-mod-selected mark {
  color: var(--jp-ui-inverse-font-color0);
}

/* Style the directory listing content when a user drops a file to upload */
.jp-DirListing.jp-mod-native-drop .jp-DirListing-content {
  outline: 5px dashed rgba(128, 128, 128, 0.5);
  outline-offset: -10px;
  cursor: copy;
}

.jp-DirListing-item {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 4px 12px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-DirListing-checkboxWrapper {
  /* Increases hit area of checkbox. */
  padding: 4px;
}

.jp-DirListing-header
  .jp-DirListing-checkboxWrapper
  + .jp-DirListing-headerItem {
  padding-left: 4px;
}

.jp-DirListing-content .jp-DirListing-checkboxWrapper {
  position: relative;
  left: -4px;
  margin: -4px 0 -4px -8px;
}

.jp-DirListing-checkboxWrapper.jp-mod-visible {
  visibility: visible;
}

/* For devices that support hovering, hide checkboxes until hovered, selected...
*/
@media (hover: hover) {
  .jp-DirListing-checkboxWrapper {
    visibility: hidden;
  }

  .jp-DirListing-item:hover .jp-DirListing-checkboxWrapper,
  .jp-DirListing-item.jp-mod-selected .jp-DirListing-checkboxWrapper {
    visibility: visible;
  }
}

.jp-DirListing-item[data-is-dot] {
  opacity: 75%;
}

.jp-DirListing-item.jp-mod-selected {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.jp-DirListing-item.jp-mod-dropTarget {
  background: var(--jp-brand-color3);
}

.jp-DirListing-item:hover:not(.jp-mod-selected) {
  background: var(--jp-layout-color2);
}

.jp-DirListing-itemIcon {
  flex: 0 0 20px;
  margin-right: 4px;
}

.jp-DirListing-itemText {
  flex: 1 0 64px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  user-select: none;
}

.jp-DirListing-itemText:focus {
  outline-width: 2px;
  outline-color: var(--jp-inverse-layout-color1);
  outline-style: solid;
  outline-offset: 1px;
}

.jp-DirListing-item.jp-mod-selected .jp-DirListing-itemText:focus {
  outline-color: var(--jp-layout-color1);
}

.jp-DirListing-itemModified {
  flex: 0 0 125px;
  text-align: right;
}

.jp-DirListing-itemFileSize {
  flex: 0 0 90px;
  text-align: right;
}

.jp-DirListing-editor {
  flex: 1 0 64px;
  outline: none;
  border: none;
  color: var(--jp-ui-font-color1);
  background-color: var(--jp-layout-color1);
}

.jp-DirListing-item.jp-mod-running .jp-DirListing-itemIcon::before {
  color: var(--jp-success-color1);
  content: '\25CF';
  font-size: 8px;
  position: absolute;
  left: -8px;
}

.jp-DirListing-item.jp-mod-running.jp-mod-selected
  .jp-DirListing-itemIcon::before {
  color: var(--jp-ui-inverse-font-color1);
}

.jp-DirListing-item.lm-mod-drag-image,
.jp-DirListing-item.jp-mod-selected.lm-mod-drag-image {
  font-size: var(--jp-ui-font-size1);
  padding-left: 4px;
  margin-left: 4px;
  width: 160px;
  background-color: var(--jp-ui-inverse-font-color2);
  box-shadow: var(--jp-elevation-z2);
  border-radius: 0;
  color: var(--jp-ui-font-color1);
  transform: translateX(-40%) translateY(-58%);
}

.jp-Document {
  min-width: 120px;
  min-height: 120px;
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Main OutputArea
| OutputArea has a list of Outputs
|----------------------------------------------------------------------------*/

.jp-OutputArea {
  overflow-y: auto;
}

.jp-OutputArea-child {
  display: table;
  table-layout: fixed;
  width: 100%;
  overflow: hidden;
}

.jp-OutputPrompt {
  width: var(--jp-cell-prompt-width);
  color: var(--jp-cell-outprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);

  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;

  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-OutputArea-prompt {
  display: table-cell;
  vertical-align: top;
}

.jp-OutputArea-output {
  display: table-cell;
  width: 100%;
  height: auto;
  overflow: auto;
  user-select: text;
  -moz-user-select: text;
  -webkit-user-select: text;
  -ms-user-select: text;
}

.jp-OutputArea .jp-RenderedText {
  padding-left: 1ch;
}

/**
 * Prompt overlay.
 */

.jp-OutputArea-promptOverlay {
  position: absolute;
  top: 0;
  width: var(--jp-cell-prompt-width);
  height: 100%;
  opacity: 0.5;
}

.jp-OutputArea-promptOverlay:hover {
  background: var(--jp-layout-color2);
  box-shadow: inset 0 0 1px var(--jp-inverse-layout-color0);
  cursor: zoom-out;
}

.jp-mod-outputsScrolled .jp-OutputArea-promptOverlay:hover {
  cursor: zoom-in;
}

/**
 * Isolated output.
 */
.jp-OutputArea-output.jp-mod-isolated {
  width: 100%;
  display: block;
}

/*
When drag events occur, `lm-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated {
  position: relative;
}

body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/* pre */

.jp-OutputArea-output pre {
  border: none;
  margin: 0;
  padding: 0;
  overflow-x: auto;
  overflow-y: auto;
  word-break: break-all;
  word-wrap: break-word;
  white-space: pre-wrap;
}

/* tables */

.jp-OutputArea-output.jp-RenderedHTMLCommon table {
  margin-left: 0;
  margin-right: 0;
}

/* description lists */

.jp-OutputArea-output dl,
.jp-OutputArea-output dt,
.jp-OutputArea-output dd {
  display: block;
}

.jp-OutputArea-output dl {
  width: 100%;
  overflow: hidden;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dt {
  font-weight: bold;
  float: left;
  width: 20%;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dd {
  float: left;
  width: 80%;
  padding: 0;
  margin: 0;
}

.jp-TrimmedOutputs pre {
  background: var(--jp-layout-color3);
  font-size: calc(var(--jp-code-font-size) * 1.4);
  text-align: center;
  text-transform: uppercase;
}

/* Hide the gutter in case of
 *  - nested output areas (e.g. in the case of output widgets)
 *  - mirrored output areas
 */
.jp-OutputArea .jp-OutputArea .jp-OutputArea-prompt {
  display: none;
}

/* Hide empty lines in the output area, for instance due to cleared widgets */
.jp-OutputArea-prompt:empty {
  padding: 0;
  border: 0;
}

/*-----------------------------------------------------------------------------
| executeResult is added to any Output-result for the display of the object
| returned by a cell
|----------------------------------------------------------------------------*/

.jp-OutputArea-output.jp-OutputArea-executeResult {
  margin-left: 0;
  width: 100%;
}

/* Text output with the Out[] prompt needs a top padding to match the
 * alignment of the Out[] prompt itself.
 */
.jp-OutputArea-executeResult .jp-RenderedText.jp-OutputArea-output {
  padding-top: var(--jp-code-padding);
  border-top: var(--jp-border-width) solid transparent;
}

/*-----------------------------------------------------------------------------
| The Stdin output
|----------------------------------------------------------------------------*/

.jp-Stdin-prompt {
  color: var(--jp-content-font-color0);
  padding-right: var(--jp-code-padding);
  vertical-align: baseline;
  flex: 0 0 auto;
}

.jp-Stdin-input {
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  color: inherit;
  background-color: inherit;
  width: 42%;
  min-width: 200px;

  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;

  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0 0.25em;
  margin: 0 0.25em;
  flex: 0 0 70%;
}

.jp-Stdin-input::placeholder {
  opacity: 0;
}

.jp-Stdin-input:focus {
  box-shadow: none;
}

.jp-Stdin-input:focus::placeholder {
  opacity: 1;
}

/*-----------------------------------------------------------------------------
| Output Area View
|----------------------------------------------------------------------------*/

.jp-LinkedOutputView .jp-OutputArea {
  height: 100%;
  display: block;
}

.jp-LinkedOutputView .jp-OutputArea-output:only-child {
  height: 100%;
}

/*-----------------------------------------------------------------------------
| Printing
|----------------------------------------------------------------------------*/

@media print {
  .jp-OutputArea-child {
    break-inside: avoid-page;
  }
}

/*-----------------------------------------------------------------------------
| Mobile
|----------------------------------------------------------------------------*/
@media only screen and (max-width: 760px) {
  .jp-OutputPrompt {
    display: table-row;
    text-align: left;
  }

  .jp-OutputArea-child .jp-OutputArea-output {
    display: table-row;
    margin-left: var(--jp-notebook-padding);
  }
}

/* Trimmed outputs warning */
.jp-TrimmedOutputs > a {
  margin: 10px;
  text-decoration: none;
  cursor: pointer;
}

.jp-TrimmedOutputs > a:hover {
  text-decoration: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Table of Contents
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toc-active-width: 4px;
}

.jp-TableOfContents {
  display: flex;
  flex-direction: column;
  background: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  height: 100%;
}

.jp-TableOfContents-placeholder {
  text-align: center;
}

.jp-TableOfContents-placeholderContent {
  color: var(--jp-content-font-color2);
  padding: 8px;
}

.jp-TableOfContents-placeholderContent > h3 {
  margin-bottom: var(--jp-content-heading-margin-bottom);
}

.jp-TableOfContents .jp-SidePanel-content {
  overflow-y: auto;
}

.jp-TableOfContents-tree {
  margin: 4px;
}

.jp-TableOfContents ol {
  list-style-type: none;
}

/* stylelint-disable-next-line selector-max-type */
.jp-TableOfContents li > ol {
  /* Align left border with triangle icon center */
  padding-left: 11px;
}

.jp-TableOfContents-content {
  /* left margin for the active heading indicator */
  margin: 0 0 0 var(--jp-private-toc-active-width);
  padding: 0;
  background-color: var(--jp-layout-color1);
}

.jp-tocItem {
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-tocItem-heading {
  display: flex;
  cursor: pointer;
}

.jp-tocItem-heading:hover {
  background-color: var(--jp-layout-color2);
}

.jp-tocItem-content {
  display: block;
  padding: 4px 0;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow-x: hidden;
}

.jp-tocItem-collapser {
  height: 20px;
  margin: 2px 2px 0;
  padding: 0;
  background: none;
  border: none;
  cursor: pointer;
}

.jp-tocItem-collapser:hover {
  background-color: var(--jp-layout-color3);
}

/* Active heading indicator */

.jp-tocItem-heading::before {
  content: ' ';
  background: transparent;
  width: var(--jp-private-toc-active-width);
  height: 24px;
  position: absolute;
  left: 0;
  border-radius: var(--jp-border-radius);
}

.jp-tocItem-heading.jp-tocItem-active::before {
  background-color: var(--jp-brand-color1);
}

.jp-tocItem-heading:hover.jp-tocItem-active::before {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapser {
  flex: 0 0 var(--jp-cell-collapser-width);
  padding: 0;
  margin: 0;
  border: none;
  outline: none;
  background: transparent;
  border-radius: var(--jp-border-radius);
  opacity: 1;
}

.jp-Collapser-child {
  display: block;
  width: 100%;
  box-sizing: border-box;

  /* height: 100% doesn't work because the height of its parent is computed from content */
  position: absolute;
  top: 0;
  bottom: 0;
}

/*-----------------------------------------------------------------------------
| Printing
|----------------------------------------------------------------------------*/

/*
Hiding collapsers in print mode.

Note: input and output wrappers have "display: block" propery in print mode.
*/

@media print {
  .jp-Collapser {
    display: none;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Header/Footer
|----------------------------------------------------------------------------*/

/* Hidden by zero height by default */
.jp-CellHeader,
.jp-CellFooter {
  height: 0;
  width: 100%;
  padding: 0;
  margin: 0;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Input
|----------------------------------------------------------------------------*/

/* All input areas */
.jp-InputArea {
  display: table;
  table-layout: fixed;
  width: 100%;
  overflow: hidden;
}

.jp-InputArea-editor {
  display: table-cell;
  overflow: hidden;
  vertical-align: top;

  /* This is the non-active, default styling */
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0;
  background: var(--jp-cell-editor-background);
}

.jp-InputPrompt {
  display: table-cell;
  vertical-align: top;
  width: var(--jp-cell-prompt-width);
  color: var(--jp-cell-inprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  opacity: var(--jp-cell-prompt-opacity);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;

  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;

  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/*-----------------------------------------------------------------------------
| Mobile
|----------------------------------------------------------------------------*/
@media only screen and (max-width: 760px) {
  .jp-InputArea-editor {
    display: table-row;
    margin-left: var(--jp-notebook-padding);
  }

  .jp-InputPrompt {
    display: table-row;
    text-align: left;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Placeholder {
  display: table;
  table-layout: fixed;
  width: 100%;
}

.jp-Placeholder-prompt {
  display: table-cell;
  box-sizing: border-box;
}

.jp-Placeholder-content {
  display: table-cell;
  padding: 4px 6px;
  border: 1px solid transparent;
  border-radius: 0;
  background: none;
  box-sizing: border-box;
  cursor: pointer;
}

.jp-Placeholder-contentContainer {
  display: flex;
}

.jp-Placeholder-content:hover,
.jp-InputPlaceholder > .jp-Placeholder-content:hover {
  border-color: var(--jp-layout-color3);
}

.jp-Placeholder-content .jp-MoreHorizIcon {
  width: 32px;
  height: 16px;
  border: 1px solid transparent;
  border-radius: var(--jp-border-radius);
}

.jp-Placeholder-content .jp-MoreHorizIcon:hover {
  border: 1px solid var(--jp-border-color1);
  box-shadow: 0 0 2px 0 rgba(0, 0, 0, 0.25);
  background-color: var(--jp-layout-color0);
}

.jp-PlaceholderText {
  white-space: nowrap;
  overflow-x: hidden;
  color: var(--jp-inverse-layout-color3);
  font-family: var(--jp-code-font-family);
}

.jp-InputPlaceholder > .jp-Placeholder-content {
  border-color: var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-cell-scrolling-output-offset: 5px;
}

/*-----------------------------------------------------------------------------
| Cell
|----------------------------------------------------------------------------*/

.jp-Cell {
  padding: var(--jp-cell-padding);
  margin: 0;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Common input/output
|----------------------------------------------------------------------------*/

.jp-Cell-inputWrapper,
.jp-Cell-outputWrapper {
  display: flex;
  flex-direction: row;
  padding: 0;
  margin: 0;

  /* Added to reveal the box-shadow on the input and output collapsers. */
  overflow: visible;
}

/* Only input/output areas inside cells */
.jp-Cell-inputArea,
.jp-Cell-outputArea {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Collapser
|----------------------------------------------------------------------------*/

/* Make the output collapser disappear when there is not output, but do so
 * in a manner that leaves it in the layout and preserves its width.
 */
.jp-Cell.jp-mod-noOutputs .jp-Cell-outputCollapser {
  border: none !important;
  background: transparent !important;
}

.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputCollapser {
  min-height: var(--jp-cell-collapser-min-height);
}

/*-----------------------------------------------------------------------------
| Output
|----------------------------------------------------------------------------*/

/* Put a space between input and output when there IS output */
.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputWrapper {
  margin-top: 5px;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea {
  overflow-y: auto;
  max-height: 24em;
  margin-left: var(--jp-private-cell-scrolling-output-offset);
  resize: vertical;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea[style*='height'] {
  max-height: unset;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea::after {
  content: ' ';
  box-shadow: inset 0 0 6px 2px rgb(0 0 0 / 30%);
  width: 100%;
  height: 100%;
  position: sticky;
  bottom: 0;
  top: 0;
  margin-top: -50%;
  float: left;
  display: block;
  pointer-events: none;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-child {
  padding-top: 6px;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  width: calc(
    var(--jp-cell-prompt-width) - var(--jp-private-cell-scrolling-output-offset)
  );
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-promptOverlay {
  left: calc(-1 * var(--jp-private-cell-scrolling-output-offset));
}

/*-----------------------------------------------------------------------------
| CodeCell
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| MarkdownCell
|----------------------------------------------------------------------------*/

.jp-MarkdownOutput {
  display: table-cell;
  width: 100%;
  margin-top: 0;
  margin-bottom: 0;
  padding-left: var(--jp-code-padding);
}

.jp-MarkdownOutput.jp-RenderedHTMLCommon {
  overflow: auto;
}

/* collapseHeadingButton (show always if hiddenCellsButton is _not_ shown) */
.jp-collapseHeadingButton {
  display: flex;
  min-height: var(--jp-cell-collapser-min-height);
  font-size: var(--jp-code-font-size);
  position: absolute;
  background-color: transparent;
  background-size: 25px;
  background-repeat: no-repeat;
  background-position-x: center;
  background-position-y: top;
  background-image: var(--jp-icon-caret-down);
  right: 0;
  top: 0;
  bottom: 0;
}

.jp-collapseHeadingButton.jp-mod-collapsed {
  background-image: var(--jp-icon-caret-right);
}

/*
 set the container font size to match that of content
 so that the nested collapse buttons have the right size
*/
.jp-MarkdownCell .jp-InputPrompt {
  font-size: var(--jp-content-font-size1);
}

/*
  Align collapseHeadingButton with cell top header
  The font sizes are identical to the ones in packages/rendermime/style/base.css
*/
.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='1'] {
  font-size: var(--jp-content-font-size5);
  background-position-y: calc(0.3 * var(--jp-content-font-size5));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='2'] {
  font-size: var(--jp-content-font-size4);
  background-position-y: calc(0.3 * var(--jp-content-font-size4));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='3'] {
  font-size: var(--jp-content-font-size3);
  background-position-y: calc(0.3 * var(--jp-content-font-size3));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='4'] {
  font-size: var(--jp-content-font-size2);
  background-position-y: calc(0.3 * var(--jp-content-font-size2));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='5'] {
  font-size: var(--jp-content-font-size1);
  background-position-y: top;
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='6'] {
  font-size: var(--jp-content-font-size0);
  background-position-y: top;
}

/* collapseHeadingButton (show only on (hover,active) if hiddenCellsButton is shown) */
.jp-Notebook.jp-mod-showHiddenCellsButton .jp-collapseHeadingButton {
  display: none;
}

.jp-Notebook.jp-mod-showHiddenCellsButton
  :is(.jp-MarkdownCell:hover, .jp-mod-active)
  .jp-collapseHeadingButton {
  display: flex;
}

/* showHiddenCellsButton (only show if jp-mod-showHiddenCellsButton is set, which
is a consequence of the showHiddenCellsButton option in Notebook Settings)*/
.jp-Notebook.jp-mod-showHiddenCellsButton .jp-showHiddenCellsButton {
  margin-left: calc(var(--jp-cell-prompt-width) + 2 * var(--jp-code-padding));
  margin-top: var(--jp-code-padding);
  border: 1px solid var(--jp-border-color2);
  background-color: var(--jp-border-color3) !important;
  color: var(--jp-content-font-color0) !important;
  display: flex;
}

.jp-Notebook.jp-mod-showHiddenCellsButton .jp-showHiddenCellsButton:hover {
  background-color: var(--jp-border-color2) !important;
}

.jp-showHiddenCellsButton {
  display: none;
}

/*-----------------------------------------------------------------------------
| Printing
|----------------------------------------------------------------------------*/

/*
Using block instead of flex to allow the use of the break-inside CSS property for
cell outputs.
*/

@media print {
  .jp-Cell-inputWrapper,
  .jp-Cell-outputWrapper {
    display: block;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-notebook-toolbar-padding: 2px 5px 2px 2px;
}

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-NotebookPanel-toolbar {
  padding: var(--jp-notebook-toolbar-padding);

  /* disable paint containment from lumino 2.0 default strict CSS containment */
  contain: style size !important;
}

.jp-Toolbar-item.jp-Notebook-toolbarCellType .jp-select-wrapper.jp-mod-focused {
  border: none;
  box-shadow: none;
}

.jp-Notebook-toolbarCellTypeDropdown select {
  height: 24px;
  font-size: var(--jp-ui-font-size1);
  line-height: 14px;
  border-radius: 0;
  display: block;
}

.jp-Notebook-toolbarCellTypeDropdown span {
  top: 5px !important;
}

.jp-Toolbar-responsive-popup {
  position: absolute;
  height: fit-content;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: flex-end;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: var(--jp-notebook-toolbar-padding);
  z-index: 1;
  right: 0;
  top: 0;
}

.jp-Toolbar > .jp-Toolbar-responsive-opener {
  margin-left: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-Notebook-ExecutionIndicator {
  position: relative;
  display: inline-block;
  height: 100%;
  z-index: 9997;
}

.jp-Notebook-ExecutionIndicator-tooltip {
  visibility: hidden;
  height: auto;
  width: max-content;
  width: -moz-max-content;
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color1);
  text-align: justify;
  border-radius: 6px;
  padding: 0 5px;
  position: fixed;
  display: table;
}

.jp-Notebook-ExecutionIndicator-tooltip.up {
  transform: translateX(-50%) translateY(-100%) translateY(-32px);
}

.jp-Notebook-ExecutionIndicator-tooltip.down {
  transform: translateX(calc(-100% + 16px)) translateY(5px);
}

.jp-Notebook-ExecutionIndicator-tooltip.hidden {
  display: none;
}

.jp-Notebook-ExecutionIndicator:hover .jp-Notebook-ExecutionIndicator-tooltip {
  visibility: visible;
}

.jp-Notebook-ExecutionIndicator span {
  font-size: var(--jp-ui-font-size1);
  font-family: var(--jp-ui-font-family);
  color: var(--jp-ui-font-color1);
  line-height: 24px;
  display: block;
}

.jp-Notebook-ExecutionIndicator-progress-bar {
  display: flex;
  justify-content: center;
  height: 100%;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*
 * Execution indicator
 */
.jp-tocItem-content::after {
  content: '';

  /* Must be identical to form a circle */
  width: 12px;
  height: 12px;
  background: none;
  border: none;
  position: absolute;
  right: 0;
}

.jp-tocItem-content[data-running='0']::after {
  border-radius: 50%;
  border: var(--jp-border-width) solid var(--jp-inverse-layout-color3);
  background: none;
}

.jp-tocItem-content[data-running='1']::after {
  border-radius: 50%;
  border: var(--jp-border-width) solid var(--jp-inverse-layout-color3);
  background-color: var(--jp-inverse-layout-color3);
}

.jp-tocItem-content[data-running='0'],
.jp-tocItem-content[data-running='1'] {
  margin-right: 12px;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-Notebook-footer {
  height: 27px;
  margin-left: calc(
    var(--jp-cell-prompt-width) + var(--jp-cell-collapser-width) +
      var(--jp-cell-padding)
  );
  width: calc(
    100% -
      (
        var(--jp-cell-prompt-width) + var(--jp-cell-collapser-width) +
          var(--jp-cell-padding) + var(--jp-cell-padding)
      )
  );
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  color: var(--jp-ui-font-color3);
  margin-top: 6px;
  background: none;
  cursor: pointer;
}

.jp-Notebook-footer:focus {
  border-color: var(--jp-cell-editor-active-border-color);
}

/* For devices that support hovering, hide footer until hover */
@media (hover: hover) {
  .jp-Notebook-footer {
    opacity: 0;
  }

  .jp-Notebook-footer:focus,
  .jp-Notebook-footer:hover {
    opacity: 1;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Imports
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-side-by-side-output-size: 1fr;
  --jp-side-by-side-resized-cell: var(--jp-side-by-side-output-size);
  --jp-private-notebook-dragImage-width: 304px;
  --jp-private-notebook-dragImage-height: 36px;
  --jp-private-notebook-selected-color: var(--md-blue-400);
  --jp-private-notebook-active-color: var(--md-green-400);
}

/*-----------------------------------------------------------------------------
| Notebook
|----------------------------------------------------------------------------*/

/* stylelint-disable selector-max-class */

.jp-NotebookPanel {
  display: block;
  height: 100%;
}

.jp-NotebookPanel.jp-Document {
  min-width: 240px;
  min-height: 120px;
}

.jp-Notebook {
  padding: var(--jp-notebook-padding);
  outline: none;
  overflow: auto;
  background: var(--jp-layout-color0);
}

.jp-Notebook.jp-mod-scrollPastEnd::after {
  display: block;
  content: '';
  min-height: var(--jp-notebook-scroll-padding);
}

.jp-MainAreaWidget-ContainStrict .jp-Notebook * {
  contain: strict;
}

.jp-Notebook .jp-Cell {
  overflow: visible;
}

.jp-Notebook .jp-Cell .jp-InputPrompt {
  cursor: move;
}

/*-----------------------------------------------------------------------------
| Notebook state related styling
|
| The notebook and cells each have states, here are the possibilities:
|
| - Notebook
|   - Command
|   - Edit
| - Cell
|   - None
|   - Active (only one can be active)
|   - Selected (the cells actions are applied to)
|   - Multiselected (when multiple selected, the cursor)
|   - No outputs
|----------------------------------------------------------------------------*/

/* Command or edit modes */

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-InputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-OutputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

/* cell is active */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser {
  background: var(--jp-brand-color1);
}

/* cell is dirty */
.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt {
  color: var(--jp-warn-color1);
}

.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt::before {
  color: var(--jp-warn-color1);
  content: '•';
}

.jp-Notebook .jp-Cell.jp-mod-active.jp-mod-dirty .jp-Collapser {
  background: var(--jp-warn-color1);
}

/* collapser is hovered */
.jp-Notebook .jp-Cell .jp-Collapser:hover {
  box-shadow: var(--jp-elevation-z2);
  background: var(--jp-brand-color1);
  opacity: var(--jp-cell-collapser-not-active-hover-opacity);
}

/* cell is active and collapser is hovered */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser:hover {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/* Command mode */

.jp-Notebook.jp-mod-commandMode .jp-Cell.jp-mod-selected {
  background: var(--jp-notebook-multiselected-color);
}

.jp-Notebook.jp-mod-commandMode
  .jp-Cell.jp-mod-active.jp-mod-selected:not(.jp-mod-multiSelected) {
  background: transparent;
}

/* Edit mode */

.jp-Notebook.jp-mod-editMode .jp-Cell.jp-mod-active .jp-InputArea-editor {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-cell-editor-active-background);
}

/*-----------------------------------------------------------------------------
| Notebook drag and drop
|----------------------------------------------------------------------------*/

.jp-Notebook-cell.jp-mod-dropSource {
  opacity: 0.5;
}

.jp-Notebook-cell.jp-mod-dropTarget,
.jp-Notebook.jp-mod-commandMode
  .jp-Notebook-cell.jp-mod-active.jp-mod-selected.jp-mod-dropTarget {
  border-top-color: var(--jp-private-notebook-selected-color);
  border-top-style: solid;
  border-top-width: 2px;
}

.jp-dragImage {
  display: block;
  flex-direction: row;
  width: var(--jp-private-notebook-dragImage-width);
  height: var(--jp-private-notebook-dragImage-height);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
  overflow: visible;
}

.jp-dragImage-singlePrompt {
  box-shadow: 2px 2px 4px 0 rgba(0, 0, 0, 0.12);
}

.jp-dragImage .jp-dragImage-content {
  flex: 1 1 auto;
  z-index: 2;
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  line-height: var(--jp-code-line-height);
  padding: var(--jp-code-padding);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background-color);
  color: var(--jp-content-font-color3);
  text-align: left;
  margin: 4px 4px 4px 0;
}

.jp-dragImage .jp-dragImage-prompt {
  flex: 0 0 auto;
  min-width: 36px;
  color: var(--jp-cell-inprompt-font-color);
  padding: var(--jp-code-padding);
  padding-left: 12px;
  font-family: var(--jp-cell-prompt-font-family);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: 1.9;
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
}

.jp-dragImage-multipleBack {
  z-index: -1;
  position: absolute;
  height: 32px;
  width: 300px;
  top: 8px;
  left: 8px;
  background: var(--jp-layout-color2);
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  box-shadow: 2px 2px 4px 0 rgba(0, 0, 0, 0.12);
}

/*-----------------------------------------------------------------------------
| Cell toolbar
|----------------------------------------------------------------------------*/

.jp-NotebookTools {
  display: block;
  min-width: var(--jp-sidebar-min-width);
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);

  /* This is needed so that all font sizing of children done in ems is
    * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  overflow: auto;
}

.jp-ActiveCellTool {
  padding: 12px 0;
  display: flex;
}

.jp-ActiveCellTool-Content {
  flex: 1 1 auto;
}

.jp-ActiveCellTool .jp-ActiveCellTool-CellContent {
  background: var(--jp-cell-editor-background);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0;
  min-height: 29px;
}

.jp-ActiveCellTool .jp-InputPrompt {
  min-width: calc(var(--jp-cell-prompt-width) * 0.75);
}

.jp-ActiveCellTool-CellContent > pre {
  padding: 5px 4px;
  margin: 0;
  white-space: normal;
}

.jp-MetadataEditorTool {
  flex-direction: column;
  padding: 12px 0;
}

.jp-RankedPanel > :not(:first-child) {
  margin-top: 12px;
}

.jp-KeySelector select.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: var(--jp-border-width) solid var(--jp-border-color1);
}

.jp-KeySelector label,
.jp-MetadataEditorTool label,
.jp-NumberSetter label {
  line-height: 1.4;
}

.jp-NotebookTools .jp-select-wrapper {
  margin-top: 4px;
  margin-bottom: 0;
}

.jp-NumberSetter input {
  width: 100%;
  margin-top: 4px;
}

.jp-NotebookTools .jp-Collapse {
  margin-top: 16px;
}

/*-----------------------------------------------------------------------------
| Presentation Mode (.jp-mod-presentationMode)
|----------------------------------------------------------------------------*/

.jp-mod-presentationMode .jp-Notebook {
  --jp-content-font-size1: var(--jp-content-presentation-font-size1);
  --jp-code-font-size: var(--jp-code-presentation-font-size);
}

.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-InputPrompt,
.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-OutputPrompt {
  flex: 0 0 110px;
}

/*-----------------------------------------------------------------------------
| Side-by-side Mode (.jp-mod-sideBySide)
|----------------------------------------------------------------------------*/
.jp-mod-sideBySide.jp-Notebook .jp-Notebook-cell {
  margin-top: 3em;
  margin-bottom: 3em;
  margin-left: 5%;
  margin-right: 5%;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell {
  display: grid;
  grid-template-columns: minmax(0, 1fr) min-content minmax(
      0,
      var(--jp-side-by-side-output-size)
    );
  grid-template-rows: auto minmax(0, 1fr) auto;
  grid-template-areas:
    'header header header'
    'input handle output'
    'footer footer footer';
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell.jp-mod-resizedCell {
  grid-template-columns: minmax(0, 1fr) min-content minmax(
      0,
      var(--jp-side-by-side-resized-cell)
    );
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellHeader {
  grid-area: header;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-Cell-inputWrapper {
  grid-area: input;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-Cell-outputWrapper {
  /* overwrite the default margin (no vertical separation needed in side by side move */
  margin-top: 0;
  grid-area: output;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellFooter {
  grid-area: footer;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellResizeHandle {
  grid-area: handle;
  user-select: none;
  display: block;
  height: 100%;
  cursor: ew-resize;
  padding: 0 var(--jp-cell-padding);
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellResizeHandle::after {
  content: '';
  display: block;
  background: var(--jp-border-color2);
  height: 100%;
  width: 5px;
}

.jp-mod-sideBySide.jp-Notebook
  .jp-CodeCell.jp-mod-resizedCell
  .jp-CellResizeHandle::after {
  background: var(--jp-border-color0);
}

.jp-CellResizeHandle {
  display: none;
}

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Cell-Placeholder {
  padding-left: 55px;
}

.jp-Cell-Placeholder-wrapper {
  background: #fff;
  border: 1px solid;
  border-color: #e5e6e9 #dfe0e4 #d0d1d5;
  border-radius: 4px;
  -webkit-border-radius: 4px;
  margin: 10px 15px;
}

.jp-Cell-Placeholder-wrapper-inner {
  padding: 15px;
  position: relative;
}

.jp-Cell-Placeholder-wrapper-body {
  background-repeat: repeat;
  background-size: 50% auto;
}

.jp-Cell-Placeholder-wrapper-body div {
  background: #f6f7f8;
  background-image: -webkit-linear-gradient(
    left,
    #f6f7f8 0%,
    #edeef1 20%,
    #f6f7f8 40%,
    #f6f7f8 100%
  );
  background-repeat: no-repeat;
  background-size: 800px 104px;
  height: 104px;
  position: absolute;
  right: 15px;
  left: 15px;
  top: 15px;
}

div.jp-Cell-Placeholder-h1 {
  top: 20px;
  height: 20px;
  left: 15px;
  width: 150px;
}

div.jp-Cell-Placeholder-h2 {
  left: 15px;
  top: 50px;
  height: 10px;
  width: 100px;
}

div.jp-Cell-Placeholder-content-1,
div.jp-Cell-Placeholder-content-2,
div.jp-Cell-Placeholder-content-3 {
  left: 15px;
  right: 15px;
  height: 10px;
}

div.jp-Cell-Placeholder-content-1 {
  top: 100px;
}

div.jp-Cell-Placeholder-content-2 {
  top: 120px;
}

div.jp-Cell-Placeholder-content-3 {
  top: 140px;
}

</style>
<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
The following CSS variables define the main, public API for styling JupyterLab.
These variables should be used by all plugins wherever possible. In other
words, plugins should not define custom colors, sizes, etc unless absolutely
necessary. This enables users to change the visual theme of JupyterLab
by changing these variables.

Many variables appear in an ordered sequence (0,1,2,3). These sequences
are designed to work well together, so for example, `--jp-border-color1` should
be used with `--jp-layout-color1`. The numbers have the following meanings:

* 0: super-primary, reserved for special emphasis
* 1: primary, most important under normal situations
* 2: secondary, next most important under normal situations
* 3: tertiary, next most important under normal situations

Throughout JupyterLab, we are mostly following principles from Google's
Material Design when selecting colors. We are not, however, following
all of MD as it is not optimized for dense, information rich UIs.
*/

:root {
  /* Elevation
   *
   * We style box-shadows using Material Design's idea of elevation. These particular numbers are taken from here:
   *
   * https://github.com/material-components/material-components-web
   * https://material-components-web.appspot.com/elevation.html
   */

  --jp-shadow-base-lightness: 0;
  --jp-shadow-umbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.2
  );
  --jp-shadow-penumbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.14
  );
  --jp-shadow-ambient-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.12
  );
  --jp-elevation-z0: none;
  --jp-elevation-z1: 0 2px 1px -1px var(--jp-shadow-umbra-color),
    0 1px 1px 0 var(--jp-shadow-penumbra-color),
    0 1px 3px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z2: 0 3px 1px -2px var(--jp-shadow-umbra-color),
    0 2px 2px 0 var(--jp-shadow-penumbra-color),
    0 1px 5px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z4: 0 2px 4px -1px var(--jp-shadow-umbra-color),
    0 4px 5px 0 var(--jp-shadow-penumbra-color),
    0 1px 10px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z6: 0 3px 5px -1px var(--jp-shadow-umbra-color),
    0 6px 10px 0 var(--jp-shadow-penumbra-color),
    0 1px 18px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z8: 0 5px 5px -3px var(--jp-shadow-umbra-color),
    0 8px 10px 1px var(--jp-shadow-penumbra-color),
    0 3px 14px 2px var(--jp-shadow-ambient-color);
  --jp-elevation-z12: 0 7px 8px -4px var(--jp-shadow-umbra-color),
    0 12px 17px 2px var(--jp-shadow-penumbra-color),
    0 5px 22px 4px var(--jp-shadow-ambient-color);
  --jp-elevation-z16: 0 8px 10px -5px var(--jp-shadow-umbra-color),
    0 16px 24px 2px var(--jp-shadow-penumbra-color),
    0 6px 30px 5px var(--jp-shadow-ambient-color);
  --jp-elevation-z20: 0 10px 13px -6px var(--jp-shadow-umbra-color),
    0 20px 31px 3px var(--jp-shadow-penumbra-color),
    0 8px 38px 7px var(--jp-shadow-ambient-color);
  --jp-elevation-z24: 0 11px 15px -7px var(--jp-shadow-umbra-color),
    0 24px 38px 3px var(--jp-shadow-penumbra-color),
    0 9px 46px 8px var(--jp-shadow-ambient-color);

  /* Borders
   *
   * The following variables, specify the visual styling of borders in JupyterLab.
   */

  --jp-border-width: 1px;
  --jp-border-color0: var(--md-grey-400);
  --jp-border-color1: var(--md-grey-400);
  --jp-border-color2: var(--md-grey-300);
  --jp-border-color3: var(--md-grey-200);
  --jp-inverse-border-color: var(--md-grey-600);
  --jp-border-radius: 2px;

  /* UI Fonts
   *
   * The UI font CSS variables are used for the typography all of the JupyterLab
   * user interface elements that are not directly user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-ui-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-ui-font-scale-factor: 1.2;
  --jp-ui-font-size0: 0.83333em;
  --jp-ui-font-size1: 13px; /* Base font size */
  --jp-ui-font-size2: 1.2em;
  --jp-ui-font-size3: 1.44em;
  --jp-ui-font-family: system-ui, -apple-system, blinkmacsystemfont, 'Segoe UI',
    helvetica, arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji',
    'Segoe UI Symbol';

  /*
   * Use these font colors against the corresponding main layout colors.
   * In a light theme, these go from dark to light.
   */

  /* Defaults use Material Design specification */
  --jp-ui-font-color0: rgba(0, 0, 0, 1);
  --jp-ui-font-color1: rgba(0, 0, 0, 0.87);
  --jp-ui-font-color2: rgba(0, 0, 0, 0.54);
  --jp-ui-font-color3: rgba(0, 0, 0, 0.38);

  /*
   * Use these against the brand/accent/warn/error colors.
   * These will typically go from light to darker, in both a dark and light theme.
   */

  --jp-ui-inverse-font-color0: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color1: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color2: rgba(255, 255, 255, 0.7);
  --jp-ui-inverse-font-color3: rgba(255, 255, 255, 0.5);

  /* Content Fonts
   *
   * Content font variables are used for typography of user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-content-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-content-line-height: 1.6;
  --jp-content-font-scale-factor: 1.2;
  --jp-content-font-size0: 0.83333em;
  --jp-content-font-size1: 14px; /* Base font size */
  --jp-content-font-size2: 1.2em;
  --jp-content-font-size3: 1.44em;
  --jp-content-font-size4: 1.728em;
  --jp-content-font-size5: 2.0736em;

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-content-presentation-font-size1: 17px;
  --jp-content-heading-line-height: 1;
  --jp-content-heading-margin-top: 1.2em;
  --jp-content-heading-margin-bottom: 0.8em;
  --jp-content-heading-font-weight: 500;

  /* Defaults use Material Design specification */
  --jp-content-font-color0: rgba(0, 0, 0, 1);
  --jp-content-font-color1: rgba(0, 0, 0, 0.87);
  --jp-content-font-color2: rgba(0, 0, 0, 0.54);
  --jp-content-font-color3: rgba(0, 0, 0, 0.38);
  --jp-content-link-color: var(--md-blue-900);
  --jp-content-font-family: system-ui, -apple-system, blinkmacsystemfont,
    'Segoe UI', helvetica, arial, sans-serif, 'Apple Color Emoji',
    'Segoe UI Emoji', 'Segoe UI Symbol';

  /*
   * Code Fonts
   *
   * Code font variables are used for typography of code and other monospaces content.
   */

  --jp-code-font-size: 13px;
  --jp-code-line-height: 1.3077; /* 17px for 13px base */
  --jp-code-padding: 5px; /* 5px for 13px base, codemirror highlighting needs integer px value */
  --jp-code-font-family-default: menlo, consolas, 'DejaVu Sans Mono', monospace;
  --jp-code-font-family: var(--jp-code-font-family-default);

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-code-presentation-font-size: 16px;

  /* may need to tweak cursor width if you change font size */
  --jp-code-cursor-width0: 1.4px;
  --jp-code-cursor-width1: 2px;
  --jp-code-cursor-width2: 4px;

  /* Layout
   *
   * The following are the main layout colors use in JupyterLab. In a light
   * theme these would go from light to dark.
   */

  --jp-layout-color0: white;
  --jp-layout-color1: white;
  --jp-layout-color2: var(--md-grey-200);
  --jp-layout-color3: var(--md-grey-400);
  --jp-layout-color4: var(--md-grey-600);

  /* Inverse Layout
   *
   * The following are the inverse layout colors use in JupyterLab. In a light
   * theme these would go from dark to light.
   */

  --jp-inverse-layout-color0: #111;
  --jp-inverse-layout-color1: var(--md-grey-900);
  --jp-inverse-layout-color2: var(--md-grey-800);
  --jp-inverse-layout-color3: var(--md-grey-700);
  --jp-inverse-layout-color4: var(--md-grey-600);

  /* Brand/accent */

  --jp-brand-color0: var(--md-blue-900);
  --jp-brand-color1: var(--md-blue-700);
  --jp-brand-color2: var(--md-blue-300);
  --jp-brand-color3: var(--md-blue-100);
  --jp-brand-color4: var(--md-blue-50);
  --jp-accent-color0: var(--md-green-900);
  --jp-accent-color1: var(--md-green-700);
  --jp-accent-color2: var(--md-green-300);
  --jp-accent-color3: var(--md-green-100);

  /* State colors (warn, error, success, info) */

  --jp-warn-color0: var(--md-orange-900);
  --jp-warn-color1: var(--md-orange-700);
  --jp-warn-color2: var(--md-orange-300);
  --jp-warn-color3: var(--md-orange-100);
  --jp-error-color0: var(--md-red-900);
  --jp-error-color1: var(--md-red-700);
  --jp-error-color2: var(--md-red-300);
  --jp-error-color3: var(--md-red-100);
  --jp-success-color0: var(--md-green-900);
  --jp-success-color1: var(--md-green-700);
  --jp-success-color2: var(--md-green-300);
  --jp-success-color3: var(--md-green-100);
  --jp-info-color0: var(--md-cyan-900);
  --jp-info-color1: var(--md-cyan-700);
  --jp-info-color2: var(--md-cyan-300);
  --jp-info-color3: var(--md-cyan-100);

  /* Cell specific styles */

  --jp-cell-padding: 5px;
  --jp-cell-collapser-width: 8px;
  --jp-cell-collapser-min-height: 20px;
  --jp-cell-collapser-not-active-hover-opacity: 0.6;
  --jp-cell-editor-background: var(--md-grey-100);
  --jp-cell-editor-border-color: var(--md-grey-300);
  --jp-cell-editor-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-cell-editor-active-background: var(--jp-layout-color0);
  --jp-cell-editor-active-border-color: var(--jp-brand-color1);
  --jp-cell-prompt-width: 64px;
  --jp-cell-prompt-font-family: var(--jp-code-font-family-default);
  --jp-cell-prompt-letter-spacing: 0;
  --jp-cell-prompt-opacity: 1;
  --jp-cell-prompt-not-active-opacity: 0.5;
  --jp-cell-prompt-not-active-font-color: var(--md-grey-700);

  /* A custom blend of MD grey and blue 600
   * See https://meyerweb.com/eric/tools/color-blend/#546E7A:1E88E5:5:hex */
  --jp-cell-inprompt-font-color: #307fc1;

  /* A custom blend of MD grey and orange 600
   * https://meyerweb.com/eric/tools/color-blend/#546E7A:F4511E:5:hex */
  --jp-cell-outprompt-font-color: #bf5b3d;

  /* Notebook specific styles */

  --jp-notebook-padding: 10px;
  --jp-notebook-select-background: var(--jp-layout-color1);
  --jp-notebook-multiselected-color: var(--md-blue-50);

  /* The scroll padding is calculated to fill enough space at the bottom of the
  notebook to show one single-line cell (with appropriate padding) at the top
  when the notebook is scrolled all the way to the bottom. We also subtract one
  pixel so that no scrollbar appears if we have just one single-line cell in the
  notebook. This padding is to enable a 'scroll past end' feature in a notebook.
  */
  --jp-notebook-scroll-padding: calc(
    100% - var(--jp-code-font-size) * var(--jp-code-line-height) -
      var(--jp-code-padding) - var(--jp-cell-padding) - 1px
  );

  /* Rendermime styles */

  --jp-rendermime-error-background: #fdd;
  --jp-rendermime-table-row-background: var(--md-grey-100);
  --jp-rendermime-table-row-hover-background: var(--md-light-blue-50);

  /* Dialog specific styles */

  --jp-dialog-background: rgba(0, 0, 0, 0.25);

  /* Console specific styles */

  --jp-console-padding: 10px;

  /* Toolbar specific styles */

  --jp-toolbar-border-color: var(--jp-border-color1);
  --jp-toolbar-micro-height: 8px;
  --jp-toolbar-background: var(--jp-layout-color1);
  --jp-toolbar-box-shadow: 0 0 2px 0 rgba(0, 0, 0, 0.24);
  --jp-toolbar-header-margin: 4px 4px 0 4px;
  --jp-toolbar-active-background: var(--md-grey-300);

  /* Statusbar specific styles */

  --jp-statusbar-height: 24px;

  /* Input field styles */

  --jp-input-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-input-active-background: var(--jp-layout-color1);
  --jp-input-hover-background: var(--jp-layout-color1);
  --jp-input-background: var(--md-grey-100);
  --jp-input-border-color: var(--jp-inverse-border-color);
  --jp-input-active-border-color: var(--jp-brand-color1);
  --jp-input-active-box-shadow-color: rgba(19, 124, 189, 0.3);

  /* General editor styles */

  --jp-editor-selected-background: #d9d9d9;
  --jp-editor-selected-focused-background: #d7d4f0;
  --jp-editor-cursor-color: var(--jp-ui-font-color0);

  /* Code mirror specific styles */

  --jp-mirror-editor-keyword-color: #008000;
  --jp-mirror-editor-atom-color: #88f;
  --jp-mirror-editor-number-color: #080;
  --jp-mirror-editor-def-color: #00f;
  --jp-mirror-editor-variable-color: var(--md-grey-900);
  --jp-mirror-editor-variable-2-color: rgb(0, 54, 109);
  --jp-mirror-editor-variable-3-color: #085;
  --jp-mirror-editor-punctuation-color: #05a;
  --jp-mirror-editor-property-color: #05a;
  --jp-mirror-editor-operator-color: #a2f;
  --jp-mirror-editor-comment-color: #408080;
  --jp-mirror-editor-string-color: #ba2121;
  --jp-mirror-editor-string-2-color: #708;
  --jp-mirror-editor-meta-color: #a2f;
  --jp-mirror-editor-qualifier-color: #555;
  --jp-mirror-editor-builtin-color: #008000;
  --jp-mirror-editor-bracket-color: #997;
  --jp-mirror-editor-tag-color: #170;
  --jp-mirror-editor-attribute-color: #00c;
  --jp-mirror-editor-header-color: blue;
  --jp-mirror-editor-quote-color: #090;
  --jp-mirror-editor-link-color: #00c;
  --jp-mirror-editor-error-color: #f00;
  --jp-mirror-editor-hr-color: #999;

  /*
    RTC user specific colors.
    These colors are used for the cursor, username in the editor,
    and the icon of the user.
  */

  --jp-collaborator-color1: #ffad8e;
  --jp-collaborator-color2: #dac83d;
  --jp-collaborator-color3: #72dd76;
  --jp-collaborator-color4: #00e4d0;
  --jp-collaborator-color5: #45d4ff;
  --jp-collaborator-color6: #e2b1ff;
  --jp-collaborator-color7: #ff9de6;

  /* Vega extension styles */

  --jp-vega-background: white;

  /* Sidebar-related styles */

  --jp-sidebar-min-width: 250px;

  /* Search-related styles */

  --jp-search-toggle-off-opacity: 0.5;
  --jp-search-toggle-hover-opacity: 0.8;
  --jp-search-toggle-on-opacity: 1;
  --jp-search-selected-match-background-color: rgb(245, 200, 0);
  --jp-search-selected-match-color: black;
  --jp-search-unselected-match-background-color: var(
    --jp-inverse-layout-color0
  );
  --jp-search-unselected-match-color: var(--jp-ui-inverse-font-color0);

  /* Icon colors that work well with light or dark backgrounds */
  --jp-icon-contrast-color0: var(--md-purple-600);
  --jp-icon-contrast-color1: var(--md-green-600);
  --jp-icon-contrast-color2: var(--md-pink-600);
  --jp-icon-contrast-color3: var(--md-blue-600);

  /* Button colors */
  --jp-accept-color-normal: var(--md-blue-700);
  --jp-accept-color-hover: var(--md-blue-800);
  --jp-accept-color-active: var(--md-blue-900);
  --jp-warn-color-normal: var(--md-red-700);
  --jp-warn-color-hover: var(--md-red-800);
  --jp-warn-color-active: var(--md-red-900);
  --jp-reject-color-normal: var(--md-grey-600);
  --jp-reject-color-hover: var(--md-grey-700);
  --jp-reject-color-active: var(--md-grey-800);

  /* File or activity icons and switch semantic variables */
  --jp-jupyter-icon-color: #f37626;
  --jp-notebook-icon-color: #f37626;
  --jp-json-icon-color: var(--md-orange-700);
  --jp-console-icon-background-color: var(--md-blue-700);
  --jp-console-icon-color: white;
  --jp-terminal-icon-background-color: var(--md-grey-800);
  --jp-terminal-icon-color: var(--md-grey-200);
  --jp-text-editor-icon-color: var(--md-grey-700);
  --jp-inspector-icon-color: var(--md-grey-700);
  --jp-switch-color: var(--md-grey-400);
  --jp-switch-true-position-color: var(--md-orange-900);
}
</style>
<style type="text/css">
/* Force rendering true colors when outputing to pdf */
* {
  -webkit-print-color-adjust: exact;
}

/* Misc */
a.anchor-link {
  display: none;
}

/* Input area styling */
.jp-InputArea {
  overflow: hidden;
}

.jp-InputArea-editor {
  overflow: hidden;
}

.cm-editor.cm-s-jupyter .highlight pre {
/* weird, but --jp-code-padding defined to be 5px but 4px horizontal padding is hardcoded for pre.cm-line */
  padding: var(--jp-code-padding) 4px;
  margin: 0;

  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
  color: inherit;

}

.jp-OutputArea-output pre {
  line-height: inherit;
  font-family: inherit;
}

.jp-RenderedText pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
}

/* Hiding the collapser by default */
.jp-Collapser {
  display: none;
}

@page {
    margin: 0.5in; /* Margin for each printed piece of paper */
}

@media print {
  .jp-Cell-inputWrapper,
  .jp-Cell-outputWrapper {
    display: block;
  }
}
</style>
<!-- Load mathjax -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-AMS_CHTML-full,Safe"> </script>
<!-- MathJax configuration -->
<script type="text/x-mathjax-config">
    init_mathjax = function() {
        if (window.MathJax) {
        // MathJax loaded
            MathJax.Hub.Config({
                TeX: {
                    equationNumbers: {
                    autoNumber: "AMS",
                    useLabelIds: true
                    }
                },
                tex2jax: {
                    inlineMath: [ ['$','$'], ["\\(","\\)"] ],
                    displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
                    processEscapes: true,
                    processEnvironments: true
                },
                displayAlign: 'center',
                CommonHTML: {
                    linebreaks: {
                    automatic: true
                    }
                }
            });

            MathJax.Hub.Queue(["Typeset", MathJax.Hub]);
        }
    }
    init_mathjax();
    </script>
<!-- End of mathjax configuration --><script type="module">
  document.addEventListener("DOMContentLoaded", async () => {
    const diagrams = document.querySelectorAll(".jp-Mermaid > pre.mermaid");
    // do not load mermaidjs if not needed
    if (!diagrams.length) {
      return;
    }
    const mermaid = (await import("https://cdnjs.cloudflare.com/ajax/libs/mermaid/10.6.0/mermaid.esm.min.mjs")).default;
    const parser = new DOMParser();

    mermaid.initialize({
      maxTextSize: 100000,
      startOnLoad: false,
      fontFamily: window
        .getComputedStyle(document.body)
        .getPropertyValue("--jp-ui-font-family"),
      theme: document.querySelector("body[data-jp-theme-light='true']")
        ? "default"
        : "dark",
    });

    let _nextMermaidId = 0;

    function makeMermaidImage(svg) {
      const img = document.createElement("img");
      const doc = parser.parseFromString(svg, "image/svg+xml");
      const svgEl = doc.querySelector("svg");
      const { maxWidth } = svgEl?.style || {};
      const firstTitle = doc.querySelector("title");
      const firstDesc = doc.querySelector("desc");

      img.setAttribute("src", `data:image/svg+xml,${encodeURIComponent(svg)}`);
      if (maxWidth) {
        img.width = parseInt(maxWidth);
      }
      if (firstTitle) {
        img.setAttribute("alt", firstTitle.textContent);
      }
      if (firstDesc) {
        const caption = document.createElement("figcaption");
        caption.className = "sr-only";
        caption.textContent = firstDesc.textContent;
        return [img, caption];
      }
      return [img];
    }

    async function makeMermaidError(text) {
      let errorMessage = "";
      try {
        await mermaid.parse(text);
      } catch (err) {
        errorMessage = `${err}`;
      }

      const result = document.createElement("details");
      result.className = 'jp-RenderedMermaid-Details';
      const summary = document.createElement("summary");
      summary.className = 'jp-RenderedMermaid-Summary';
      const pre = document.createElement("pre");
      const code = document.createElement("code");
      code.innerText = text;
      pre.appendChild(code);
      summary.appendChild(pre);
      result.appendChild(summary);

      const warning = document.createElement("pre");
      warning.innerText = errorMessage;
      result.appendChild(warning);
      return [result];
    }

    async function renderOneMarmaid(src) {
      const id = `jp-mermaid-${_nextMermaidId++}`;
      const parent = src.parentNode;
      let raw = src.textContent.trim();
      const el = document.createElement("div");
      el.style.visibility = "hidden";
      document.body.appendChild(el);
      let results = null;
      let output = null;
      try {
        const { svg } = await mermaid.render(id, raw, el);
        results = makeMermaidImage(svg);
        output = document.createElement("figure");
        results.map(output.appendChild, output);
      } catch (err) {
        parent.classList.add("jp-mod-warning");
        results = await makeMermaidError(raw);
        output = results[0];
      } finally {
        el.remove();
      }
      parent.classList.add("jp-RenderedMermaid");
      parent.appendChild(output);
    }

    void Promise.all([...diagrams].map(renderOneMarmaid));
  });
</script>
<style>
  .jp-Mermaid:not(.jp-RenderedMermaid) {
    display: none;
  }

  .jp-RenderedMermaid {
    overflow: auto;
    display: flex;
  }

  .jp-RenderedMermaid.jp-mod-warning {
    width: auto;
    padding: 0.5em;
    margin-top: 0.5em;
    border: var(--jp-border-width) solid var(--jp-warn-color2);
    border-radius: var(--jp-border-radius);
    color: var(--jp-ui-font-color1);
    font-size: var(--jp-ui-font-size1);
    white-space: pre-wrap;
    word-wrap: break-word;
  }

  .jp-RenderedMermaid figure {
    margin: 0;
    overflow: auto;
    max-width: 100%;
  }

  .jp-RenderedMermaid img {
    max-width: 100%;
  }

  .jp-RenderedMermaid-Details > pre {
    margin-top: 1em;
  }

  .jp-RenderedMermaid-Summary {
    color: var(--jp-warn-color2);
  }

  .jp-RenderedMermaid:not(.jp-mod-warning) pre {
    display: none;
  }

  .jp-RenderedMermaid-Summary > pre {
    display: inline-block;
    white-space: normal;
  }
</style>
<!-- End of mermaid configuration --></head>
<body class="jp-Notebook" data-jp-theme-light="true" data-jp-theme-name="JupyterLab Light">
<main>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<center>
<img alt="No description has been provided for this image" src="https://hyperight.com/wp-content/uploads/2024/07/Meta-Llama-31-1024x576.webp" width='4500"'/>
</center>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p><a href="https://hyperight.com/wp-content/uploads/2024/07/Meta-Llama-31-1024x576.webp">Image Reference</a></p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f9f9f9; border: 1px solid #ddd; padding: 20px; text-align: center; font-family: Arial, sans-serif;">
<h3 style="margin-bottom: 20px;">Muhammad Imran Zaman</h3>
<a href="https://www.kaggle.com/muhammadimran112233" style="text-decoration: none; margin-right: 20px;">
<img alt="Kaggle Profile" height="100" src="https://www.kaggle.com/static/images/site-logo.svg" width="100"/>
</a>
<a href="https://www.linkedin.com/in/muhammad-imran-zaman" style="text-decoration: none; margin-right: 20px;">
<img alt="LinkedIn Profile" height="50" src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/LinkedIn_logo_initials.png/600px-LinkedIn_logo_initials.png" width="50"/>
</a>
<a href="https://scholar.google.com/citations?user=ulVFpy8AAAAJ&amp;hl=en" style="text-decoration: none; margin-right: 20px;">
<img alt="Google Scholar Profile" height="50" src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c7/Google_Scholar_logo.svg/768px-Google_Scholar_logo.svg.png" width="50"/>
</a>
<a href="https://www.youtube.com/@consolioo" style="text-decoration: none; margin-right: 20px;">
<img alt="YouTube Channel" height="50" src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/72/YouTube_social_white_square_%282017%29.svg/640px-YouTube_social_white_square_%282017%29.svg.png" width="50"/>
</a>
<a href="https://github.com/Imran-ml" style="text-decoration: none; margin-right: 20px;">
<img alt="GitHub Profile" height="50" src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="50"/>
</a>
<a href="https://imranzaman-5202.medium.com/" style="text-decoration: none; margin-right: 20px;">
<img alt="Medium Profile" height="50" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAeFBMVEUAAAD///+3t7f8/Pzs7Oz39/d6enpPT0/IyMjy8vL19fWtra04ODhxcXHU1NSqqqpeXl6Xl5fc3NwJCQl/f38WFhbm5uaPj4/AwMArKyuFhYVNTU1kZGQREREyMjJFRUUiIiKgoKBoaGgnJyc9PT2MjIwcHBxWVlbgTdlVAAAEsUlEQVR4nO3c6XqqMBAGYHDD3dbj1rpUu9j7v8NTCAhhnYQZofZ7f/LEmGHJRoLjAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQJtdp95hNpsd9qdj00Xh9zHoLEdubDSfDP41XSg+h04yuFhv4TVdNA6nST83vDDIy9Usu9VuMx7NF98yhbVwmJeEp+zeyLkdO/GpWQmWmm6/rIzPNzzRsltpv1qeRctOsR6S4vNNKPl10r96ko6gwis5vh/jQ2V+Off7IC/ddL67T2NU/QDqOhX55d4QOVfx2nXdjUhEOq+sAs3XeynLcJL/o2kmYXAmLmKBRQbG8flKmoD3otOSTngKDnclg/NdrAIseK5868KfpG/u8Fq/yga4sAzQdYsauZJaOdUtGqujc9EAL9YBFl3Fp5Jf6LWKFx1eCwb4XCNA133Py3JT9gvthrzdPoU3fH2zWgG6bk4frjzLfjLprRNV1fjY+6wZoF5gpfQS6g/v7WCmkmWTP04ykakkyp5CX+JJ9OKjUqPPTN/RwnMqz8rubdyObuODQp3WqtNNo3duitvCyC7vBKfPExPzvlqepZbntvoHt7SJ0ZpMVXNhCTBV1VfUM1r6xBleZotX35UpQK0+fSGkH0aJE8dGEhFyVDNK4iH6IiSPOtpe8qBAgGyXULuIpImCsOLUhjSf/BEWDOGsxF2xLiX5QqXVOowz/ghJZSG6dUneSMnDakV7TL7YA1wV/b2VaFBEaCt8KrF2R/OP800nZspFzdmOllydEG3ycldcVDvVXQ8jUV3ToyVXz63WKR4Wl9WO0eQhQXibEh9uNeGqdanYm3z69C+Nqh6pg7F59nSwj5/GzBGqS1A0x5YWhHPWDnHPt52YAwyrR/KUiJ94Khohb1vhCx5E8rTd2cm0ncwRcnZolKB6JD/deyfVLWWfbuOuaMLqkfZ6zlUDqNT4u/QtgTnCKM7Q0Chb/4of9EPMXW/OTqkSTDCRJ7a2TmbWkf5uuaEIe0bZ+r3Q1PugPWuA5/z/rSMYpJNTL6QjpMw1GOrXjZB3KYtAhN2Hj7Bl1/Dxn0N6UchaVpf+gfawDX2a1FAru06jlqb7pf7coWy/1H51QhGzsYVfccqOLfjHh99GJ+7sSI8P+RvEINsWjfEff56m4bk2dT5k59q450vDl/Mtmi9tds5bvYaRnfNu9r2F6qHJvrf4A++e2vb+UGAB5uO/A2YcI3K8x2fueAf41mJs40zbtBaD7yK2dj2Nc2GKsLVromTWtRE637e04uva0m8OLOnboI6V6XPXJm7TZWPSyPrSeCmp/PpScj+yBNMaYakAU6NQC61f500esxYxXquvNQt3WKt///0W2j6bS3RUcL9FS/bMyG5BtA+Rbd+TUHt/Y3uj/pq9a7Zbgzj2H4Z1uWRwyv7R95A6ze0DPt5pH7BjOL3Yt9rLnTuMn86H9/rixpE4T+b+1v34PzzRbyp8yBae6Jv1uxjXxHcxRDstRk6Tsnc2I9Nvm7zuNv3RvG2ffXkq+j7NpGUFreO8euhvDEXWU+89+E7U9AG/EwUAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAJ/wFTZUNtMEP4sAAAAABJRU5ErkJggg==" width="50"/>
</a>
<a href="https://huggingface.co/ImranzamanML" style="text-decoration: none;">
<img alt="Hugging Face Profile" height="100" src="https://huggingface.co/datasets/huggingface/brand-assets/resolve/main/hf-logo-with-title.svg" width="200"/>
</a>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div class="alert alert-block alert-info">
<h2><center><strong>Building a Mental Health Chatbot by fine tuning Llama 3.1</strong></center></h2>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;">
<strong>Mental health</strong> is a critical aspect of overall well being for emotional, psychological and social dimensions.
    
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p style="font-family: Comic Sans MS, cursive, sans-serif; color: #333; font-size: 16px;">
    Let's find some mental peace 😊 by fine tuning Llama 3.1.
</p>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="o">!</span>pip<span class="w"> </span>install<span class="w"> </span>-qqq<span class="w"> </span><span class="s2">"unsloth[colab-new] @ git+https://github.com/unslothai/unsloth.git"</span><span class="w"> </span>--progress-bar<span class="w"> </span>off
<span class="o">!</span>pip<span class="w"> </span>install<span class="w"> </span>-qqq<span class="w"> </span>--no-deps<span class="w"> </span><span class="s2">"xformers&lt;0.0.24"</span><span class="w"> </span><span class="s2">"trl&lt;0.9.0"</span><span class="w"> </span>peft<span class="w"> </span>accelerate<span class="w"> </span>bitsandbytes<span class="w"> </span>--progress-bar<span class="w"> </span>off
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;">
<p><strong>We are going to use Unsloth</strong> because it significantly enhances the efficiency of fine-tuning large language models (LLMs) specially LLaMA and Mistral. With Unsloth, we can use advanced quantization techniques, such as <strong>4-bit</strong> and <strong>16-bit quantization</strong>, to reduce the memory and speed up both training and inference. This means we can deploy powerful models even on hardware with limited resources but without compromising on performance.</p>
<p> Additionally, Unsloth broad compatibility and customization options allow to do the quantization process to fit the specific needs of products. This flexibility combined with its ability to cut <strong>VRAM usage by up to 60%</strong>, makes Unsloth an essential tool in AI toolkit. Its not just about optimizing models its about making cutting-edge AI more accessible and efficient for real world applications.</p>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="For-fine-tuning,-I-used-the-following-setup:">For fine tuning, I used the following setup:<a class="anchor-link" href="#For-fine-tuning,-I-used-the-following-setup:">¶</a></h4><ul style="margin1 20px; padding: 10px; list-style-type: disc;">
<li><strong><a href="https://pytorch.org/" target="_blank">Torch 2.1.1 with CUDA 12.1</a></strong> for efficient computation.</li>
<li><strong><a href="https://github.com/unslothai/unsloth" target="_blank">Unsloth</a></strong> to achieve 2X faster training speeds for the large language model (LLM).</li>
<li><strong><a href="https://www.nvidia.com/content/dam/en-zz/Solutions/Data-Center/h100/PB-11773-001_v01.pdf" target="_blank">  H100 NVL GPU</a></strong> to handle the intensive processing requirement but you can use the less power GPU as well.</li>
</ul>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<ul style="margin: 10px; padding: 10px; list-style-type: disc;">
<strong><a href="https://llama.meta.com/" target="_blank">Why LLaMA 3.1?</a></strong>
<p><strong>Its Open Source and Accessible</strong> and offers the flexibility to customize and fine-tune it with the specific needs. Due to open source weights of the model from Meta, it is very easy to fine tune on any problem and we are going to fine tune it on mental health dataset from the <strong><a href="https://huggingface.co/datasets/Amod/mental_health_counseling_conversations" target="_blank">Hugging Face</a></strong></p>
</ul></div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h2 style="font-family: Arial, sans-serif; color: #4CAF50; border-bottom: 2px solid #4CAF50; padding-bottom: 5px; margin-bottom: 20px;">
    Python Libraries 📕 📗 📘 📙
</h2>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Data Handling and Visualization</span>
<span class="kn">import</span> <span class="nn">os</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="n">plt</span><span class="o">.</span><span class="n">style</span><span class="o">.</span><span class="n">use</span><span class="p">(</span><span class="s1">'ggplot'</span><span class="p">)</span>

<span class="c1"># LLM model training</span>
<span class="kn">import</span> <span class="nn">torch</span>
<span class="kn">from</span> <span class="nn">trl</span> <span class="kn">import</span> <span class="n">SFTTrainer</span>
<span class="kn">from</span> <span class="nn">transformers</span> <span class="kn">import</span> <span class="n">TrainingArguments</span><span class="p">,</span> <span class="n">TextStreamer</span>
<span class="kn">from</span> <span class="nn">unsloth.chat_templates</span> <span class="kn">import</span> <span class="n">get_chat_template</span>
<span class="kn">from</span> <span class="nn">unsloth</span> <span class="kn">import</span> <span class="n">FastLanguageModel</span><span class="p">,</span> <span class="n">is_bfloat16_supported</span>
<span class="kn">from</span> <span class="nn">datasets</span> <span class="kn">import</span> <span class="n">Dataset</span>

<span class="c1"># Saving model</span>
<span class="kn">from</span> <span class="nn">transformers</span> <span class="kn">import</span> <span class="n">AutoTokenizer</span><span class="p">,</span> <span class="n">AutoModelForSequenceClassification</span>

<span class="c1"># Warnings</span>
<span class="kn">import</span> <span class="nn">warnings</span>
<span class="n">warnings</span><span class="o">.</span><span class="n">filterwarnings</span><span class="p">(</span><span class="s2">"ignore"</span><span class="p">)</span>

<span class="o">%</span><span class="k">matplotlib</span> inline
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h2 style="font-family: Arial, sans-serif; color: #4CAF50; border-bottom: 2px solid #4CAF50; padding-bottom: 5px; margin-bottom: 20px;">
    Calling the dataset
</h2>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_json</span><span class="p">(</span><span class="s2">"hf://datasets/Amod/mental_health_counseling_conversations/combined_dataset.json"</span><span class="p">,</span> <span class="n">lines</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h2 style="font-family: Arial, sans-serif; color: #4CAF50; border-bottom: 2px solid #4CAF50; padding-bottom: 5px; margin-bottom: 20px;">
    Exploratory data analysis 🔎 📊
</h2>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Five-top-records-of-data">Five top records of data<a class="anchor-link" href="#Five-top-records-of-data">¶</a></h4>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">data</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[ ]:</div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<style scoped="">
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Context</th>
<th>Response</th>
</tr>
</thead>
<tbody>
<tr>
<th>0</th>
<td>I'm going through some things with my feelings...</td>
<td>If everyone thinks you're worthless, then mayb...</td>
</tr>
<tr>
<th>1</th>
<td>I'm going through some things with my feelings...</td>
<td>Hello, and thank you for your question and see...</td>
</tr>
<tr>
<th>2</th>
<td>I'm going through some things with my feelings...</td>
<td>First thing I'd suggest is getting the sleep y...</td>
</tr>
<tr>
<th>3</th>
<td>I'm going through some things with my feelings...</td>
<td>Therapy is essential for those that are feelin...</td>
</tr>
<tr>
<th>4</th>
<td>I'm going through some things with my feelings...</td>
<td>I first want to let you know that you are not ...</td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Length-of-data">Length of data<a class="anchor-link" href="#Length-of-data">¶</a></h4>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s1">'lenght of data is'</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">data</span><span class="p">))</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>lenght of data is 3512
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Shape-of-data">Shape of data<a class="anchor-link" href="#Shape-of-data">¶</a></h4>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">data</span><span class="o">.</span><span class="n">shape</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[ ]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>(3512, 2)</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Checking-Null-values">Checking Null values<a class="anchor-link" href="#Checking-Null-values">¶</a></h4>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">data</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span><span class="o">.</span><span class="n">any</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">))</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[ ]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>0</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Rows-and-columns-in-the-dataset">Rows and columns in the dataset<a class="anchor-link" href="#Rows-and-columns-in-the-dataset">¶</a></h4>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s1">'Count of columns in the data is:  '</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">data</span><span class="o">.</span><span class="n">columns</span><span class="p">))</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Count of columns in the data is:   2
</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s1">'Count of rows in the data is:  '</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">data</span><span class="p">))</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Count of rows in the data is:   3512
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Lets-check-the-lenght-of-words-in-each-context">Lets check the lenght of words in each context<a class="anchor-link" href="#Lets-check-the-lenght-of-words-in-each-context">¶</a></h4>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">data</span><span class="p">[</span><span class="s1">'Context_length'</span><span class="p">]</span> <span class="o">=</span> <span class="n">data</span><span class="p">[</span><span class="s1">'Context'</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="nb">len</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span> <span class="mi">3</span><span class="p">))</span>
<span class="n">sns</span><span class="o">.</span><span class="n">histplot</span><span class="p">(</span><span class="n">data</span><span class="p">[</span><span class="s1">'Context_length'</span><span class="p">],</span> <span class="n">bins</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span> <span class="n">kde</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">'Distribution of Context Lengths'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">'Length of Context'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">'Frequency'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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oYdKre/bty/jxo2rtPc+Nzc3cHsIwFlnncXIkSM1CWMNc6L2MHr0aJ544gk2bdrE4cOHSUxMpEOHDlxzzTUl3mu1h7ph6NChZa4fO3Ys/fr1Ayrv/wa1h5rvZO2hqKhInw+1gJIpERERERGRIOiZKRERERERkSAomRIREREREQmCkikREREREZEgKJkSEREREREJgpIpERERERGRICiZEhERERERCYKSKRERERERkSAomRIREREREQmCPdQBiIhI9fn000959tlnmTJlCq1atQp1OKUcPHiQJUuWcM4559CiRYsS25555hm++uorZs2aVeVxvPXWWyxbtozMzEwiIiKYOXPmCcv//PPPfPjhh6xbt46cnBycTiepqamcd955nHfeeURERFRJnNu3b+eLL76gX79+NG7cuErq8Fu0aBHh4eH069evSusREalNlEyJiEiNkZmZydy5c2ncuHGpZKq6fPPNN7z77rtceeWVdOnSBYfDccLys2fPZu7cubRr145rrrmG5ORkCgsLWbduHXPmzGHnzp0MHz68SmLdvn07c+fOpUOHDlWeTC1evJjY2FglUyIixSiZEhERKWbbtm0AXHLJJcTHx5+w7JdffsncuXPp378/Y8aMwbKswLauXbsycOBA1q9fX6XxiohI6CiZEhGRUnbt2sXs2bP56aefyMvLo0mTJlx00UVcfPHFgTJr1qzhoYce4i9/+Qvbtm3j008/paCggNatWzNy5EiaNm0aKGuMISMjgyVLlpCdnU1qairXX3897777LgAPPvhg4HgAzz77LM8++ywAQ4YMYejQoYFj7d69m1deeYW1a9cSExNDz549ue66607ag+T1evnvf//LJ598wt69e4mKiqJLly5cd911NGzYEIBx48axb98+AEaPHl1m/cXNnTuX6Ohobr755hKJlF9kZCSdO3cOLBcVFTF37lxWrFjBwYMHiYuL4+yzz+a6664jOjo6UG7cuHGkpqZy8cUX8+abb7J9+3aSkpK44oor6N+/P3D0lk0gcN0Axo4dG+g9WrVqFfPmzeO3337D4/GQnp7O0KFDOfPMMwHf+3z33XfTuXNn/vrXvwaOsXr1ah5++GEGDx7MtddeW+K6+K9FUlISzzzzzAmvuYhIXadkSkRESti+fTv33XcfjRo14qabbiIhIYH//e9/vPLKKxw6dIirr766RPk333yTdu3aMWbMGPLz83njjTeYOnUq06ZNw2azBcrMmzePCy64gHPOOYcDBw7w3HPP4fF4SElJASA9PZ2xY8fy7LPPcuWVV9KtWzeAQKID4PF4mDp1Kv379+fyyy/n559/5p133iEqKoohQ4ac8LxmzJjBkiVLuPjii+nWrRv79u3j7bffZs2aNUydOpW4uDjuuOMOFi1axMcff8y9995LVFRUifqLy8zMZNu2bfTq1Yvw8PCTXldjDE888QSrV69m0KBBnHHGGWzZsoXZs2ezYcMGJk+eXCIh3LJlC6+99hqDBg0iPj6epUuX8txzz5GcnEz79u3p1q0b1113HW+++SYjR44kPT0dgOTkZAA+++wznnnmGbp37864ceMICwvjo48+4pFHHmHChAmceeaZpKSkMGbMGKZPn86CBQu49NJLycrK4qmnnuKMM84IJE533HEHTz75JFFRUYwcORLgpMmriEh9oGRKRERKePXVV4mMjGTSpElERUUB0KlTJ9xuN/PmzeOSSy4hJiYmUL5Zs2b85S9/CSzbbDamTZvGr7/+Stu2bcnNzeWDDz6gV69e/PGPfwyUS01N5b777gskU1FRUaSmpgK+hKBt27alYnO73QwdOpSePXsCcOaZZ/Lbb7+xfPnyEyZTO3bsYMmSJVx44YWMGDEisD49PZ17772XDz74gOuuu4709HQaNGgAQMuWLYmLizvuMffv3w9Q7meVfvzxR3788UduvPFGrrjiCsB3XRs2bMj06dNZtmwZF1xwQaB8Tk4ODz/8MI0aNQLgjDPOYPXq1Sxfvpz27dsTFxcXuHbNmjUrcb0KCwuZOXMm3bp148477wys79q1K3fddRdvvvlmoHeqV69erF27ltdff53WrVvz1ltvAXDrrbcGkuH09HScTieRkZFlvi8iIvWVhkYXEZGAoqIiVq9ezdlnn014eDgejyfw6tq1Ky6Xiw0bNpTYp3v37iWWmzdvDhxNNjZs2IDL5QokQH5t27YlKSmpQvFZlsVZZ51Vqj7/LWjHs2bNGoBSgye0bt2a0047jdWrV1cojmD46zg2hp49exIeHl4qhhYtWgQSKQCn00lKSkrgup7IunXryM3NpW/fviXeQ2MMXbp04bfffqOgoCBQftiwYaSmpvLQQw+xZs0axo8fT2Ji4imcrYhI/aCeKRERCcjNzcXj8bBw4UIWLlxYZplDhw6VWI6NjS2xbLf7/mspKioqUb6swRwSEhIqFJ/T6cTpdJaqz+VynXA/fwxlJQgNGjQ4aTJWFn+is3fv3nKVz83NJSwsrFRvl2VZJCQknPS6gu/WOv91PZHs7GwAnnzyyRPG4x+y3eFw0Lt3b15//XXS09Pp1KnTSesQERElUyIiUkx0dDQ2m43zzjuPiy66qMwyFR2C258U+L/gF5eVlVXh3qlg+GPIzMws9QzUwYMHy0xcTiYxMZG0tDR+/PFHCgsLT/rcVExMDB6Ph5ycnBIJlTGGrKysSp33y38+I0aMoE2bNmWWKZ7Ibt26ldmzZ9OqVSt+++033n//fS6//PJKi0dEpK7SbX4iIhIQHh5Ohw4d2LRpE82bN6dVq1alXhVNPNq0aYPD4eCLL74osX79+vWleoT8gxqUp/elIjp27AjA559/XmL9r7/+yo4dOwLPD1XUVVddxeHDh3nllVcwxpTaXlBQwI8//ggQqOOzzz4rUebrr7+msLAwqBiO7QX0O/3004mOjmb79u1lvoetWrUK7FtQUMC0adNISkpi4sSJXHzxxbzxxhulbue02+2V/r6IiNR26pkSEamHVq9eXeatbV27duXmm2/m/vvv54EHHuDCCy8kKSmJ/Px8du/ezXfffcfEiRMrVFdMTAyXXXYZ8+bNIzo6mnPOOYeDBw8yZ84cEhMTSwwp3qRJE5xOJ59//jmnnXYaERERJCYmBgaFCFbTpk254IILWLhwIZZl0bVr18Bofg0bNuSyyy4L6rg9e/Zk69atvPPOO+zYsYP+/fvTpEkTioqK2LBhA0uWLKFnz5507tyZTp060blzZ9544w3y8/Np165doEcoPT2d8847r8L1p6WlAbBkyRIiIyNxOBw0btyY2NhYbr75Zp555hlyc3M599xziYuLIycnhy1btpCTkxMY+v3FF19k//79PProo0RERHDTTTexfv16pk+fzuOPPx4Ysj0tLY0vvviCL774gsaNG+N0OgP1i4jUV0qmRETqoTfeeKPM9f/6179o1qwZU6dO5Z133uGtt94iOzub6OhoUlJS6Nq1a1D1XXfddURERPDRRx/x6aefctpppzF69GjefPPNEvMrhYeHc8sttzB37lwmT56Mx+M54TxPFTFq1CiaNGnCxx9/zKJFiwLzTF1//fVB3ebnd80113DmmWeycOFC3nrrLXJycnA6naSmpnLZZZcxYMAAwPds1J133smcOXP49NNPeffdd4mLi+O8884r1zxZZWncuDHDhw9nwYIFPPjgg3i93sA8U+eddx6NGjXivffe44UXXiA/P5/4+HhatGgRGARj6dKlfP7554wdOzYwkqLdbue2227jrrvu4tlnnw2MBjh06FCysrJ4/vnnyc/P1zxTIiKAZcq6L0FERKSK7d27l9tuu40hQ4Zw5ZVXhjocERGRClPPlIiIVLnNmzezYsUK2rVrR2RkJDt37uS9994jMjKS/v37hzo8ERGRoCiZEhGRKhcREcHGjRv5+OOPycvLIyoqivbt23PddddVeHh0ERGRmkK3+YmIiIiIiARBQ6OLiIiIiIgEQcmUiIiIiIhIEJRMiYiIiIiIBEHJlIiIiIiISBCUTImIiIiIiARByZSIiIiIiEgQlEyJiIiIiIgEQcmUiIiIiIhIEP4/SZfmRX99IxQAAAAASUVORK5CYII="/>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;"> <strong>Note:</strong> : As we can see above, the least number of words are 1500, and then there is a significant difference, so we are just going to use the data with 1500 words or less.
    
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">filtered_data</span> <span class="o">=</span> <span class="n">data</span><span class="p">[</span><span class="n">data</span><span class="p">[</span><span class="s1">'Context_length'</span><span class="p">]</span> <span class="o">&lt;=</span> <span class="mi">1500</span><span class="p">]</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">ln_Context</span> <span class="o">=</span> <span class="n">filtered_data</span><span class="p">[</span><span class="s1">'Context'</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="nb">len</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span> <span class="mi">3</span><span class="p">))</span>
<span class="n">sns</span><span class="o">.</span><span class="n">histplot</span><span class="p">(</span><span class="n">ln_Context</span><span class="p">,</span> <span class="n">bins</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span> <span class="n">kde</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">'Distribution of Context Lengths'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">'Length of Context'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">'Frequency'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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OW94vV6efvppwDcSXUlUrVqV66+/no8++oju3buzadMm1qxZ499ut9tL1HNQEj///HORzxItWrQI8H3hzFexYkUA/vzzz0LlTzapbP6zJSWJv3Xr1ni9XpYsWVJo25IlS/B4PLRp06bYxyuJ/OvNv/7jud1uli1bBnDG57/99ttxOBx8/PHHrFu37pRlc3NzixXf5s2b2blzJ8nJyWc08t3p2uySSy4hNTW1yBHpTubQoUPcdNNNOJ1OvvnmG2655RbmzZtX5BxagbxnSiIqKoqmTZuydu1af09yWch/H69YsaLQtvz30YnK8tpDQ0Pp2LEjTz75JC+//DLGGGbNmlXq5xGRs0fJlIicF/bv38+gQYNYtGgRSUlJPPzww6csn5uby8KFCwv95dvlcvm/3B3/UHzlypVJSUkhJyen1GNPT0/nySefLLDuxx9/ZOrUqcTExNCvXz//+vxJZd9+++0Cf23/888/Cx3j+NjzyxTX0KFDAXjooYfIysryr8/KyvIPoT1s2LBiH68k+vbtS6VKlfjggw/47rvvCmx78cUX2bJlC1dcccUZTzZcu3ZtHn/8cfLy8ujdu/dJk9G5c+fSs2dP/3J+3YwdO5aUlBT/eo/Hw/3334/X6z3juqlYsSKWZZ20ze69914A7rjjDv+Excc7cuRIobobMmQIO3fuZMKECTRr1ozXX3+d+vXr88gjjxQqG8h7pqTuu+8+8vLyGDp0aJG9qqmpqUU+l1cSt912G+AbLOT4nub09HSeeuqpIvcp7WtfunRpkbek5veMnTj4hoiUL3pmSkTKnccffxzw9USlpaWxdu1ali1bRl5eHu3atWPq1KmnHY0vOzubK664gtq1a9O+fXtq1apFTk4OX331FevXr+eaa66hSZMm/vKXX345P/zwAz179uTSSy/F6XTSsmVLrr322jO+ni5dujBx4kS+//57OnXq5J9nyuv18sYbbxS4na5du3Z069aNRYsW0a5dO7p3786+ffv47LPPuPrqq4v8Anj55Zfz3HPPcccdd3DDDTcQFRVFbGwsf//7308a080338zs2bP56KOPaNq0KX379sWyLGbNmsXWrVsZOHAgt9xyyxlfe1GioqJ46623GDBgAF27dmXAgAEkJSXx008/MX/+fOLj43njjTdK5VwPP/yw/9mjiy++mI4dO9K2bVuioqLYt28fS5YsYdOmTQUGG+jYsSP//Oc/efbZZ2nWrBn9+/cnMjKSL7/8kjVr1tC5c2f+8Y9/nFFcUVFRtG/fniVLlnDrrbdSv3597HY71113HS1atODyyy/nmWee4aGHHqJ+/fr06tWL5ORkMjMz2b59O4sXL6Zz587MnTsX8CWhn332GQMGDGDEiBH+c0ybNo0OHTpw00038csvv/h70zp06EBERAQvvvgiBw8e9D9fdOeddxb79sUhQ4acdNtrr73G0KFD+emnn3jttdeoW7cuV199NUlJSRw6dIitW7eyZMkSbr/9dl5//fWA6/G2225j2rRpzJ07l2bNmnHdddfhcrn4+OOPadu2LRs2bCg0mt5ll12GzWbjoYce4rfffvP3Bj/yyCMBxfD8888zf/58unXrRp06dYiKimLt2rV8+eWXxMbG8pe//CXg6xORc8BZHYhdROQMcHSOmfyX0+k0lStXNm3atDHDhw83X3755UnnbDlxLqW8vDwzfvx406NHD5OYmGhCQ0NNlSpVTPv27c1///vfAnPSGOObX+mvf/2rqVGjhrHb7YXmAKKI+WqOd6p5pgYPHmzWr19vrrvuOhMbG2vCw8NNx44dzdy5c4s8VlpamvnLX/5i4uLijNPpNE2bNjVvvPHGKecmev75502jRo2M0+n0z5F0srrJ5/F4zKuvvmouuugiEx4ebsLDw02bNm3Mf/7znyLr+VR1cLq5roqycuVK07dvX1OlShXjcDhMYmKi+etf/2p27dpVqGwg80wdb926debvf/+7adq0qYmOjjYOh8PEx8ebHj16mIkTJ5qcnJxC+3zwwQemU6dOJioqyoSGhpomTZqYsWPHFpozyZhTz1N2snmNNm3aZK655hpTqVIlY1lWkfM+LV261AwYMMAkJCQYh8NhqlSpYlq2bGnuvfde88MPPxhjjPnxxx+N0+k0ycnJheakMsaYl156yQDm+uuvL7D+yy+/NJdccomJjIz0f+aK034nfk6LeqWmpvrLf/bZZ6Z3794mLi7OOBwOU61aNXPxxReb0aNHm/Xr1xc6dknfY9nZ2ebRRx81tWvXNk6n09SqVcs8/PDDZufOnQYwffv2LXSsKVOmmJYtW5qwsLBC82ad6r1c1Ptw3rx5ZsiQIaZx48amQoUKJiIiwjRo0MDceeedZtu2baetTxE5t1nGBOHJUxEREZEg+uqrr7jqqqt48MEHGTduXLDDEZFySs9MiYiIyHmrqGfKDh486H/274YbbjjbIYnIeUTPTImIiMh567777mPVqlV07NiRuLg4du7cyZdffsmhQ4cYOXJkkZPviogUl5IpEREROW/dcMMNHDhwgDlz5nDo0CFCQ0Np1qwZw4YNK7MRKUXkwqFnpkRERERERAKgZ6ZEREREREQCoGRKREREREQkAEqmREREREREAqBkSkREREREJAAaze8EqampuN3uUj9uXFwcKSkppX5cKT61QXCp/oNPbRBcqv/gUxsEn9oguFT/xRcSEkLFihVPX+4sxFKuuN1uXC5XqR7Tsiz/sTV4YnCoDYJL9R98aoPgUv0Hn9og+NQGwaX6Lxu6zU9ERERERCQASqZEREREREQCoGRKREREREQkAEqmREREREREAqBkSkREREREJABKpkRERERERAKgZEpERERERCQASqZEREREREQCcE5N2jtz5kw++OADevXqxZAhQwAwxjB9+nQWLlxIZmYm9evXZ9iwYSQmJvr3c7lcTJkyheXLl5OXl0ezZs0YPnw4lStXDtKVyOk4vB5wBzg5cogDl81eugGJiIiIiJTQOZNMbd68mQULFlCrVq0C62fPns0XX3zByJEjSUhI4JNPPmHs2LG8+OKLhIeHAzB58mR++ukn7r77bqKjo3n33Xd55plnGD9+PDabOt/OSW4XuXM/CWjX0B7Xg1PJlIiIiIgE1zmRaeTk5PDKK68wYsQIIiMj/euNMcyZM4d+/frRvn17kpKSGDVqFLm5uSxbtgyArKwsvv76a2677TZatGhBcnIyd955Jzt27GD16tXBuiQRERERETnPnRM9UxMnTqR169a0aNGCTz451luxf/9+0tLSaNmypX+dw+GgSZMmbNiwgSuvvJItW7bg8Xho0aKFv0ylSpVISkpi48aNtGrVqshzulwuXK5jt5lZluXv6bIsq1SvL/94pX3c8i/w+ihpXaoNgkv1H3xqg+BS/Qef2iD41AbBpfovG0FPppYvX87WrVsZN25coW1paWkAxMTEFFgfExPDgQMH/GVCQkKIiooqVCZ//6LMnDmTGTNm+JeTk5MZP348cXFxAV7J6cXHx5fZscub9N07cUZHnb5gUZxO4hISAtpVbRBcqv/gUxsEl+o/+NQGwac2CC7Vf+kKajJ14MABJk+e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jRkzhqZNmwKq/zN1us/AiUaNGkWvXr0KTNqrNihdSqZEREREREQCoGemREREREREAqBkSkREREREJABKpkRERERERAKgZEpERERERCQASqZEREREREQCoGRKREREREQkAEqmREREREREAqBkSkREREREJAAhwQ5ARETOnkWLFvHaa68xbtw46tatG+xwCjl06BALFiygXbt21K5du8C2V199le+++44pU6aUeRzTpk1j8eLFpKamEhYWxuTJk09Zfv369Xz55Zds2LCBjIwMnE4niYmJdOnShS5duhAWFlYmce7cuZMVK1bQrVs3qlatWibnyDdv3jxCQ0Pp1q1bmZ5HRKQ8UTIlIiLnjNTUVGbMmEHVqlULJVNnyw8//MAnn3zC9ddfT6tWrXA4HKcs/9FHHzFjxgwaNmzIjTfeSHx8PLm5uWzYsIHp06eze/duhgwZUiax7ty5kxkzZtC0adMyT6bmz59PdHS0kikRkeMomRIRETnOn3/+CUDPnj2JiYk5Zdlvv/2WGTNm0L17d0aMGIFlWf5trVu3pk+fPmzcuLFM4xURkeBRMiUiIoXs2bOHjz76iN9++42srCyqVavG1VdfTY8ePfxl1q5dyxNPPMFdd93Fn3/+yaJFi8jJyaFevXoMGzaM6tWr+8saY5g5cyYLFiwgPT2dxMREbr75Zj755BMAHn/8cf/xAF577TVee+01APr378/AgQP9x9q7dy9vv/0269atIyoqig4dOnDTTTedtgfJ6/Xy2Wef8c0337B//34iIiJo1aoVN910E5UrVwZg1KhRpKSkAHDHHXcUef7jzZgxg8jISG6//fYCiVS+8PBwWrZs6V/Oy8tjxowZLF++nEOHDlGhQgUuvvhibrrpJiIjI/3lRo0aRWJiIj169OCDDz5g586dxMXFcd1119G9e3fg2C2bgL/eAEaOHOnvPVq9ejWzZs3ijz/+wOPxkJyczMCBA2nevDnga+cHH3yQli1bct999/mPsWbNGp566in69evHoEGDCtRLfl3ExcXx6quvnrLORUTOd0qmRESkgJ07d/LII49QpUoVbrvtNmJjY/n11195++23OXz4MAMGDChQ/oMPPqBhw4aMGDGC7Oxspk6dyvjx45kwYQI2m81fZtasWVxxxRW0a9eOgwcP8vrrr+PxeEhISAAgOTmZkSNH8tprr3H99dfTpk0bAH+iA+DxeBg/fjzdu3fnmmuuYf369Xz88cdERETQv3//U17XxIkTWbBgAT169KBNmzakpKTw4YcfsnbtWsaPH0+FChW4//77mTdvHl9//TUPP/wwERERBc5/vNTUVP788086duxIaGjoaevVGMNzzz3HmjVr6Nu3L40bN2b79u189NFHbNq0ibFjxxZICLdv3867775L3759iYmJYeHChbz++uvEx8fTpEkT2rRpw0033cQHH3zAsGHDSE5OBiA+Ph6AJUuW8Oqrr9K2bVtGjRqF3W7nq6++4umnn2b06NE0b96chIQERowYwYsvvsicOXPo1asXaWlpvPTSSzRu3NifON1///288MILREREMGzYMIDTJq8iIhcCJVMiIlLAO++8Q3h4OE8++SQREREAtGjRArfbzaxZs+jZsydRUVH+8jVr1uSuu+7yL9tsNiZMmMDmzZtp0KABmZmZfPHFF3Ts2JG//OUv/nKJiYk88sgj/mQqIiKCxMREwJcQNGjQoFBsbrebgQMH0qFDBwCaN2/OH3/8wbJly06ZTO3atYsFCxZw1VVXMXToUP/65ORkHn74Yb744gtuuukmkpOTqVSpEgB16tShQoUKJz3mgQMHAIr9rNKqVatYtWoVt956K9dddx3gq9fKlSvz4osvsnjxYq644gp/+YyMDJ566imqVKkCQOPGjVmzZg3Lli2jSZMmVKhQwV93NWvWLFBfubm5TJ48mTZt2vCPf/zDv75169Y88MADfPDBB/7eqY4dO7Ju3Tree+896tWrx7Rp0wC4++67/clwcnIyTqeT8PDwIttFRORCpaHRRUTELy8vjzVr1nDxxRcTGhqKx+Pxv1q3bo3L5WLTpk0F9mnbtm2B5Vq1agHHko1Nmzbhcrn8CVC+Bg0aEBcXV6L4LMvioosuKnS+/FvQTmbt2rUAhQZPqFevHjVq1GDNmjUliiMQ+ec4MYYOHToQGhpaKIbatWv7EykAp9NJQkKCv15PZcOGDWRmZtK1a9cCbWiMoVWrVvzxxx/k5OT4yw8ePJjExESeeOIJ1q5dy5133knFihXP4GpFRC4M6pkSERG/zMxMPB4Pc+fOZe7cuUWWOXz4cIHl6OjoAsshIb7/teTl5RUoX9RgDrGxsSWKz+l04nQ6C53P5XKdcr/8GIpKECpVqnTaZKwo+YnO/v37i1U+MzMTu91eqLfLsixiY2NPW6/gu7Uuv15PJT09HYAXXnjhlPHkD9nucDjo1KkT7733HsnJybRo0eK05xARESVTIiJynMjISGw2G126dOHqq68uskxJh+DOTwryv+AfLy0trcS9U4HIjyE1NbXQM1CHDh0qMnE5nYoVK5KUlMSqVavIzc097XNTUVFReDweMjIyCiRUxhjS0tJKdd6v/OsZOnQo9evXL7LM8Ynsjh07+Oijj6hbty5//PEHn3/+Oddcc02pxSMicr7SbX4iIuIXGhpK06ZN2bp1K7Vq1aJu3bqFXiVNPOrXr4/D4WDFihUF1m/cuLFQj1D+oAbF6X0piWbNmgGwdOnSAus3b97Mrl27/M8PldQNN9zAkSNHePvttzHGFNqek5PDqlWrAPznWLJkSYEy33//Pbm5uQHFcGIvYL5GjRoRGRnJzp07i2zDunXr+vfNyclhwoQJxMXFMWbMGHr06MHUqVML3c4ZEhJS6u0iIlLeqWdKROQCtGbNmiJvbWvdujW33347jz76KI899hhXXXUVcXFxZGdns3fvXn766SfGjBlTonNFRUXRu3dvZs2aRWRkJO3atePQoUNMnz6dihUrFhhSvFq1ajidTpYuXUqNGjUICwujYsWK/kEhAlW9enWuuOIK5s6di2VZtG7d2j+aX+XKlendu3dAx+3QoQM7duzg448/ZteuXXTv3p1q1aqRl5fHpk2bWLBgAR06dKBly5a0aNGCli1bMnXqVLKzs2nYsKG/Ryg5OZkuXbqU+PxJSUkALFiwgPDwcBwOB1WrViU6Oprbb7+dV199lczMTC655BIqVKhARkYG27dvJyMjwz/0+//+9z8OHDjAv/71L8LCwrjtttvYuHEjL774Is8++6x/yPakpCRWrFjBihUrqFq1Kk6n039+EZELlZIpEZEL0NSpU4tc/5///IeaNWsyfvx4Pv74Y6ZNm0Z6ejqRkZEkJCTQunXrgM530003ERYWxldffcWiRYuoUaMGd9xxBx988EGB+ZVCQ0P529/+xowZMxg7diwej+eU8zyVxPDhw6lWrRpff/018+bN888zdfPNNwd0m1++G2+8kebNmzN37lymTZtGRkYGTqeTxMREevfuzZVXXgn4no36xz/+wfTp01m0aBGffPIJFSpUoEuXLsWaJ6soVatWZciQIcyZM4fHH38cr9frn2eqS5cuVKlShU8//ZQ333yT7OxsYmJiqF27tn8QjIULF7J06VJGjhzpH0kxJCSEe+65hwceeIDXXnvNPxrgwIEDSUtL44033iA7O1vzTImIAJYp6r4EERGRMrZ//37uuece+vfvz/XXXx/scEREREpMPVMiIlLmtm3bxvLly2nYsCHh4eHs3r2bTz/9lPDwcLp37x7s8ERERAKiZEpERMpcWFgYW7Zs4euvvyYrK4uIiAiaNGnCTTfdVOLh0UVERM4Vus1PREREREQkABoaXUREREREJABKpkRERERERAKgZEpERERERCQASqZEREREREQCoGRKREREREQkAEqmREREREREAqBkSkREREREJABKpkRERERERALw/wEkvjiOJ01NSwAAAABJRU5ErkJggg=="/>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;"> <strong>Note:</strong> : Now its fine to use this data.
    
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Lets-check-now-the-lenght-of-words-in-each-Response">Lets check now the lenght of words in each Response<a class="anchor-link" href="#Lets-check-now-the-lenght-of-words-in-each-Response">¶</a></h4>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">ln_Response</span> <span class="o">=</span> <span class="n">filtered_data</span><span class="p">[</span><span class="s1">'Response'</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="nb">len</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span> <span class="mi">3</span><span class="p">))</span>
<span class="n">sns</span><span class="o">.</span><span class="n">histplot</span><span class="p">(</span><span class="n">ln_Response</span><span class="p">,</span> <span class="n">bins</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span> <span class="n">kde</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">'teal'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">'Distribution of Response Lengths'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">'Length of Response'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">'Frequency'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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DhkyRAwNDRWVSqUYFBQktmvXTnz11VfFw4cPV3SpbcZZ2b/bn3eWn58vzpo1S2zfvr3o7e0tenp6is2aNRP79+8vLlq0yOrZVTW9BhZ//vmnOGjQINHPz09Uq9Vily5dxE2bNokff/yxCEBcv369Vfva/M648/NS099XRORaBFG8o3+aiIiI6t3SpUvx4osvYsmSJRX26pDr+dvf/obly5fj9OnTaNmypbPDISIXxHu4iIiIiCpRWlpqczbIHTt2YNWqVYiLi2OxRUQV4j1cRERERJUwGAyIiIhA79690apVKygUCpw6dQrbtm2Dh4dHuXvriIhux4KLiIiIqBJKpRLjxo3Drl27cPjwYej1egQFBWHIkCF466230K5dO2eHSEQujPdwERERERER1RHew0VERERERFRHWHARERERERHVERZcREREREREdYQFFxERERERUR3hLIV2yM3NhclkcnYYCA4ORlZWlrPDoGpivtwHc+VemC/3wVy5F+bLvTBf9U+hUMDf37/qdvUQS4NjMplgNBqdGoMgCFIsnGjS9TFf7oO5ci/Ml/tgrtwL8+VemC/XxiGFREREREREdYQFFxERERERUR1hwUVERERERFRHWHARERERERHVERZcREREREREdYQFFxERERERUR1hwXWXybl5E+d0OmeHQURERER0V2DBdRcRRRHP/u9/6Ld2LS7m5zs7HCIiIiKiBs/pDz5OTk7Gxo0bkZqaitzcXEyZMgWdOnWS1g8dOtTmds899xyeeOIJAMCMGTOQnJxstb5bt26YPHmy9Fqv12PJkiU4cuQIAKBjx44YOXIkvL29HXxGruucToeTOTkAgIMZGWjm6+vkiIiIiIiIGjanF1wlJSVo1qwZevfujU8++aTc+q+++srq9bFjx/Dll1+ic+fOVsv79u2LZ555RnqtUqms1n/++efIycnBtGnTAACLFi3C/PnzMXXqVEedisvbeumS9POp7GwgNtaJ0RARERERNXxOL7gSEhKQkJBQ4XqtVmv1+vDhw4iLi0Pjxo2tlnt4eJRra3HlyhUcP34cs2bNQkxMDABg7NixePvtt3Ht2jWEhYXZ3M5oNMJoNEqvBUGAl5eX9LMzWY5fkzi2paVJP5+6ccPp53A3sSdf5BzMlXthvtwHc+VemC/3wny5NqcXXDWh0+lw7NgxjB8/vty6ffv2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H3/8MVJTU1FYWAh/f3/ExcXhmWeescoDc1U/hg4danP5uHHj0KtXLwD1+7uP+apcVfkyGAz8fLmIf//73zh58iRyc3OhVqvRtGlTDBw4UCqW+LlqeFhwERERERER1RHew0VERERERFRHWHARERERERHVERZcREREREREdYQFFxERERERUR1hwUVERERERFRHWHARERERERHVERZcREREREREdYQFFxERERERUR1RODsAIiKqX7t378bChQvx4YcfIjo62tnhlHPjxg1s374dnTp1QrNmzazWLViwAL/++isSExPrPI6VK1diz549yM3NhaenJ5YuXWqz3erVq7FmzRrptVwuh1arRbt27TBs2DBotdo6j5WIiFwXCy4iInIpubm5WLNmDRo1alSu4Kovhw8fxrp16/DUU08hPj4eSqWyym3eeustqNVqFBcX48SJE/jhhx+QkpKCjz76CAoF/3dLRHS34v8BiIiI7nD58mUAwKOPPgo/P79qbdO8eXP4+voCANq2bYv8/Hzs3r0bp0+fRps2beosViIicm0suIiIyKb09HSsXr0af/zxB4qKitC4cWM8/PDDeOSRR6Q2p06dwsyZMzFx4kRcvnwZu3fvRnFxMVq0aIFRo0YhLCxMaiuKIpKSkrB9+3bk5eUhIiICzz77LNatWwcAmDFjhrQ/AFi4cCEWLlwIABg8eDCGDh0q7SsjIwNLlixBcnIyNBoNunbtiuHDh1fZE1VaWooffvgBu3btQmZmJtRqNeLj4zF8+HAEBgYCAMaPH4+srCwAwJgxY2wevzqio6Oxe/du5OXlWS0/ceIE1q9fj/Pnz8NsNiMqKgpDhw7FvffeK7XJz8/HihUrcPz4ceTl5cHLywthYWEYMmQI2rZtK12vgoICjB49Gv/9739x8eJFaDQa9O7dG0OHDoVM9tdt2nq9HitXrsThw4eRn5+PwMBAdO/eHYMHD7a6ZkOHDsXDDz+MmJgYJCUlISsrC6GhoRg2bBg6dOhQo/iqe65ERA0dCy4iIirnypUrePvttxEUFITnn38eWq0Wx48fx5IlS1BQUIAhQ4ZYtV+xYgVatmyJsWPH4ubNm/juu+8wZ84czJ07V/riv2LFCqxfvx79+vVDp06dkJOTgy+//BJmsxmhoaEAgKioKIwbNw4LFy7EU089hfbt2wOAVAwBgNlsxpw5c9CnTx8MGDAAf/75J9auXQu1Wo3BgwdXel5ff/01tm/fjkceeQTt27dHVlYWVq1ahVOnTmHOnDnw9fXFlClTsGXLFuzcuVMaJnj78asrMzMTAKRzA4C9e/diwYIF6NixI8aPHw+5XI5t27Zh1qxZmDZtmlSIzJ8/H6mpqRg2bBjCwsJQWFiI1NRU6PV6q2PodDrMmzcPTz75JIYOHYqjR49i3bp1KCwsxKhRowAABoMBM2fOREZGBoYOHYqmTZvizz//xPr163Hx4kW8+eabVvs8evQozp8/j6FDh8LT0xMbN27Ev/71L8ybNw+NGzeudnzVPVciooaOBRcREZXz7bffwsvLC++99x7UajWAW8PkTCYT1q9fj0cffRQajUZqHx4ejokTJ0qvZTIZ5s6di3PnziE2NhZ6vR4//vgjunXrhpdeeklqFxERgbffflsqStRqNSIiIgAAISEhiI2NLRebyWTC0KFD0bVrVwDAvffei/Pnz2P//v2VFlxXr17F9u3b8dBDD2HkyJHS8qioKLz11lv48ccfMXz4cERFRSEgIACA9TDBqpSWlsJsNkv3cG3duhXdu3dH8+bNAQAlJSVYunQp2rdvj9dee03aLiEhAW+88QZWrFghFSFnzpxBnz590K9fP6ndfffdV+6YBQUFeP3119GxY0cAQLt27WAwGLB161YMHDgQQUFB2LNnDy5duoRXX31VumZt27aFp6cnvvvuO5w4ccKqV8pgMOCdd96Bl5eXdH3Gjh2LX375BU8++WS14qvJuRIRNXScFp6IiKwYDAacPHkS9913Hzw8PGA2m6V/CQkJMBqNOHv2rNU2li/8Fk2bNgUAZGdnAwDOnj0Lo9EofeG3iI2NRXBwcI3iEwTBanib5XiWYYAVOXXqFACgV69eVstbtGiBJk2a4OTJkzWK404vvfQShg8fjhdffBFz585F8+bNMX78eGn9mTNnoNfr0bNnT6trKooi4uPjcf78eRQXF0sx7dmzB2vXrkVKSgpMJpPNY3p5eZW79j169IAoikhOTgYAnDx5Eh4eHujSpYtVO8t1+OOPP6yWx8XFScUWAGi1Wvj5+Vld36riq8m5EhE1dOzhIiIiK3q9HmazGT/99BN++uknm20KCgqsXvv4+Fi9tszKZzAYrNrbmoCiptOmq1QqqFSqcsczGo2VbmeJwd/fv9y6gICAKgu2qrzzzjtQq9XQ6/XYvn07Dh48iMWLF0s9epZ7uT799NMK96HX6+Hp6YnJkydj3bp12LlzJ1atWgVPT0906tQJzz33nNX1qux6Wob36fV6aLVaCIJg1c7Pzw9yubzKXAKAUqmUcgmgyvhqcq5ERA0dCy4iIrLi7e0NmUyGBx54AA8//LDNNo0aNarRPi1f4u+cQAK4dR9STXu57GGJITc3t9w9WTdu3LBZaNRE06ZNrWYpnDVrFnbs2IE+ffqgRYsW0v5HjhyJmJgYm/uwFEu+vr544YUX8MILLyA7OxtHjhzBd999h7y8PEybNk1qX9H1BCAN+dRoNDh79ixEUbQquvLy8mA2m6s9ZPJ2VcVXk3MlImroOKSQiIiseHh4IC4uDqmpqWjatCmio6PL/atpcRITEwOlUomff/7ZanlKSkq5niXLrHm396g4gmVq9n379lktP3fuHK5everQe4oEQcCoUaMgk8mwatUqAECrVq3g7e2NK1eu2Lym0dHRNp/XFRQUhEceeQRt27ZFamqq1bqbN2/iyJEjVsv2798PQRDQunVrALfucSsuLsbhw4et2u3ZswcAaj1lva347D1XIqKGiL/tiIjuUidPnrQ5jC4hIQEvvvgi3nnnHbz77rt46KGHEBwcjJs3byIjIwO//fYbpk+fXqNjaTQaPPbYY1i/fj28vb3RqVMn3LhxA99//z38/f2tel4aN24MlUqFffv2oUmTJvD09IS/v780kYW9wsLC0K9fP/z0008QBAEJCQnSLIWBgYF47LHHarX/O4WGhqJv377YunUrTp8+jVatWuHFF1/EggULoNfr0aVLF/j6+iI/Px+XLl1Cfn4+xowZg6KiIsycORPdu3dHkyZN4OXlhXPnzuH48ePo3Lmz1TF8fHzwn//8B9nZ2QgNDcWxY8ewY8cOPPTQQwgKCgIAPPDAA9iyZQsWLFiAzMxMREZG4vTp00hKSkJCQoLVhBnVUZ34PD09q3WuRER3AxZcRER3qe+++87m8i+++ALh4eGYM2cO1q5di5UrVyIvLw/e3t4IDQ1FQkKCXccbPnw4PD09sW3bNuzevRtNmjTBmDFjsGLFCnh7e0vtPDw88Morr2DNmjV4//33YTab7XoOli2jR49G48aNsXPnTmzZskV6Dtezzz5b6yGFtgwZMgR79+7FqlWrMH36dDzwwAMICgrCxo0b8dVXX+HmzZvw8/NDs2bNpEkslEolWrRogX379iEzMxNmsxlBQUEYOHAgBg4caLV/rVaLUaNGITExEWlpadBoNBg0aJDVtVKpVJg+fTpWrFiBH374Afn5+QgICMDjjz9ebnr/6qhufNU5VyKiu4EgiqLo7CCIiOjulJmZicmTJ2Pw4MF46qmnnB2OW7E8+PiTTz5xdihERFQJ9nAREVG9uHjxIg4cOICWLVvCy8sL165dw8aNG+Hl5YU+ffo4OzwiIqI6wYKLiIjqhaenJy5cuICdO3eiqKgIarUarVu3xvDhwzljHRERNVgcUkhERERERFRHOC08ERERERFRHWHBRUREREREVEdYcBEREREREdURFlxERERERER1hAUXERERERFRHWHBRUREREREVEdYcBEREREREdURFlxERERERER15P8Dg9SxpRCgN5kAAAAASUVORK5CYII="/>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;"> <strong>Note:</strong> : Here is also after 4000 words lenght response, there are is significant fall.
    
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">filtered_data</span> <span class="o">=</span> <span class="n">filtered_data</span><span class="p">[</span><span class="n">ln_Response</span> <span class="o">&lt;=</span> <span class="mi">4000</span><span class="p">]</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">ln_Response</span> <span class="o">=</span> <span class="n">filtered_data</span><span class="p">[</span><span class="s1">'Response'</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="nb">len</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span> <span class="mi">3</span><span class="p">))</span>
<span class="n">sns</span><span class="o">.</span><span class="n">histplot</span><span class="p">(</span><span class="n">ln_Response</span><span class="p">,</span> <span class="n">bins</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span> <span class="n">kde</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">'teal'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">'Distribution of Response Lengths'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">'Length of Response'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">'Frequency'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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4+OD0NBQXLhwocZCS6/XQ6/Xm18LggCVSmX+3pEqz+/oOFqCqrkWG6H1iT/D/8P72n6Ya/thru2HubYv5tt+mGv7sXeunarQEkUR3333Hdq2bYvQ0FDz8vj4ePTp0wd+fn7Izs7GqlWrMHfuXMyfPx9yuRwajQYymaxacebl5QWNRlPjuRISErB27Vrz64iICCxYsAD+/v6Ncm3WCAwMdHQIzUp5djY8PDxqXHf7vVOVRBBq3e9OFAoFggIC6r1fc8f72n6Ya/thru2HubYv5tt+mGv7sVeunarQWrx4MdLT0zF37lyL5X379jV/HxoaiqioKEyfPh2nTp1Cr169aj3enVooxowZgxEjRphfV1a2OTk5MBgM1l6CTQiCgMDAQGRlZTVKK0tLpTMaq40uKAgC3N3dodVqa821SRTvOCphrefT6ZCZmWlVrM0R72v7Ya7th7m2H+bavphv+2Gu7ac+uZbJZA1ugHGaQmvJkiU4efIk5syZc9eRAr29veHv72/+EKtWq2EwGKDVai1aJgoLCxEXF1fjMeRyOeRyeY3rnOUmF0XRaWJprirz21h55s+vOt7X9sNc2w9zbT/MtX0x3/bDXNuPvXLt8J76oihi8eLFOHr0KN59910E1OFRq6KiIty8eRPe3t4AgMjISEilUiQmJpq3yc/PR3p6OmJjYxstdiIiIiIiopo4vEVr8eLFOHToEF577TWoVCpznypXV1coFAqUlZVh9erV6N27N9RqNXJycrBy5Up4eHigZ8+e5m0HDx6MFStWwMPDA+7u7lixYgVCQ0MtBsggIiIiIiKyB4cXWjt27AAAvPfeexbLp0+fjoEDB0IikeDq1as4cOAAiouL4e3tjQ4dOuDll182jxIIAM888wykUikWLlxonrD49ddf5xxaRERERERkdw4vtFavXn3H9QqFotpcW7VtN2nSJEyaNMlWoREREREREVmFzT1EREREREQ2xkKLiIiIiIjIxlhoERERERER2RgLLSIiIiIiIhtjoUVERERERGRjLLSIiIiIiIhsjIUWERERERGRjbHQIiIiIiIisjEWWkRERERERDYmc3QARE1BmcGArJIS3CguRrnRCLFiuVQQ4KtSwV+lgo9SCYkgODROIiIiInIOLLSIaqHV6fB7Tg42pKbiUkHBXbeXCgKC3d3R1tsbMd7edoiQiIiIiJwV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"/>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f9f9f9; border-left: 6px solid #4CAF50; padding: 10px; margin: 20px 0;">
<strong>Note:</strong> There is no need for such data preparation to handle the lengths of text for LLM models, but for consistency in the number of words, I just took under 4000 words as example so you can do any data preprocessing as per needs.
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h2 style="font-family: Arial, sans-serif; color: #4CAF50; border-bottom: 2px solid #4CAF50; padding-bottom: 5px; margin-bottom: 20px;">
   Model training 🧪
</h2>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<img alt="No description has been provided for this image" src="https://miro.medium.com/v2/resize:fit:1400/1*mjbBdZ1-p7cKQkp-bU7aCg.gif"/>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p><a href="https://miro.medium.com/v2/resize:fit:1400/1*mjbBdZ1-p7cKQkp-bU7aCg.gif">Image Reference</a></p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<blockquote>
<p>Lets deep dive into Llama 3.1 model and train it on our data</p>
</blockquote>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3 id="Loading-the-model">Loading the model<a class="anchor-link" href="#Loading-the-model">¶</a></h3>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;"> We are going to use Llama 3.1 with 8 billion parameters, but you can use the 70 billion version as well. However, you cannot use the 405 billion parameter version yet with Unsloth because it doesn't support it yet. When support for the 405 billion version is available, you will be able to use it by simply replacing the number!
</div>
<h3 style="color: #388e3c; font-family: Arial, sans-serif;">Key aspects which can be followed as per your requirement as well:</h3>
<ol style="margin-left: 20px;">
<li><strong>Max Sequence Length:</strong>
<p>We used <code>max_seq_length</code> 5020, the maximum number of tokens can be used in model that can handle in a single input sequence. This is crucial for tasks requiring the processing of long texts, ensuring that the model can capture more context in each pass. It can be used as per requirements.</p>
</li>
<li><strong>Loading Llama 3.1 Model:</strong>
<p>The model and tokenizer are loaded using <code>FastLanguageModel.from_pretrained</code> with a specific pre-trained model, <code>"unsloth/Meta-Llama-3.1-8B-bnb-4bit"</code>. This is optimized for 4-bit precision, which reduces memory usage and increases training speed without significantly compromising performance. The <code>load_in_4bit=True</code> parameter enables this efficient 4-bit quantization, making it more suitable for fine-tuning on less powerful hardware.</p>
</li>
<li><strong>Applying PEFT (Parameter-Efficient Fine-Tuning):</strong>
<p>Then we configured model using <code>get_peft_model</code>, which applies LoRA (Low-Rank Adaptation) techniques. This approach focuses on fine-tuning only specific layers or parts of the model, rather than the entire network, drastically reducing the computational resources needed.</p>
<p>Parameters such as <code>r=16</code> and <code>lora_alpha=16</code> adjust the complexity and scaling of these adaptations. The use of <code>target_modules</code> specifies which layers of the model should be adapted, which include key components involved in attention mechanisms like <code>q_proj</code>, <code>k_proj</code>, and <code>v_proj</code>.</p>
<p><code>use_rslora=True</code> activates Rank-Stabilized LoRA, which improves the stability of the fine-tuning process. <code>use_gradient_checkpointing="unsloth"</code> ensures that memory usage is optimized during training by selectively storing only necessary computations, further enhancing the model's efficiency.</p>
</li>
<li><strong>Verifying Trainable Parameters:</strong>
<p>Finally we are using <code>model.print_trainable_parameters()</code> to print out the number of parameters that will be updated during fine-tuning, allowing to verify that only the intended parts of the model are being trained.</p>
</li>
</ol>
<p>This combination of techniques makes the fine-tuning process not only more efficient but also more accessible, allowing you to deploy this model even with limited computational resources.</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<blockquote>
<p>Setting maximum lenght of tokenz 5020 is more than enough as Low-Rank Adaptation (LoRA) for training but you can use as per your data and requirements.</p>
</blockquote>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">max_seq_length</span> <span class="o">=</span> <span class="mi">5020</span>
<span class="n">model</span><span class="p">,</span> <span class="n">tokenizer</span> <span class="o">=</span> <span class="n">FastLanguageModel</span><span class="o">.</span><span class="n">from_pretrained</span><span class="p">(</span>
    <span class="n">model_name</span><span class="o">=</span><span class="s2">"unsloth/Meta-Llama-3.1-8B-bnb-4bit"</span><span class="p">,</span>
    <span class="n">max_seq_length</span><span class="o">=</span><span class="n">max_seq_length</span><span class="p">,</span>
    <span class="n">load_in_4bit</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
    <span class="n">dtype</span><span class="o">=</span><span class="kc">None</span><span class="p">,</span>
<span class="p">)</span>

<span class="n">model</span> <span class="o">=</span> <span class="n">FastLanguageModel</span><span class="o">.</span><span class="n">get_peft_model</span><span class="p">(</span>
    <span class="n">model</span><span class="p">,</span>
    <span class="n">r</span><span class="o">=</span><span class="mi">16</span><span class="p">,</span>
    <span class="n">lora_alpha</span><span class="o">=</span><span class="mi">16</span><span class="p">,</span>
    <span class="n">lora_dropout</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>
    <span class="n">target_modules</span><span class="o">=</span><span class="p">[</span><span class="s2">"q_proj"</span><span class="p">,</span> <span class="s2">"k_proj"</span><span class="p">,</span> <span class="s2">"v_proj"</span><span class="p">,</span> <span class="s2">"up_proj"</span><span class="p">,</span> <span class="s2">"down_proj"</span><span class="p">,</span> <span class="s2">"o_proj"</span><span class="p">,</span> <span class="s2">"gate_proj"</span><span class="p">],</span>
    <span class="n">use_rslora</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
    <span class="n">use_gradient_checkpointing</span><span class="o">=</span><span class="s2">"unsloth"</span>
<span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">model</span><span class="o">.</span><span class="n">print_trainable_parameters</span><span class="p">())</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>==((====))==  Unsloth 2024.8: Fast Llama patching. Transformers = 4.44.1.
   \\   /|    GPU: NVIDIA H100 NVL. Max memory: 93.003 GB. Platform = Linux.
O^O/ \_/ \    Pytorch: 2.1.1. CUDA = 9.0. CUDA Toolkit = 12.1.
\        /    Bfloat16 = TRUE. FA [Xformers = 0.0.23.post1. FA2 = False]
 "-____-"     Free Apache license: http://github.com/unslothai/unsloth
</pre>
</div>
</div>
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr" tabindex="0">
<pre>Unsloth 2024.8 patched 32 layers with 32 QKV layers, 32 O layers and 32 MLP layers.
</pre>
</div>
</div>
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>trainable params: 41,943,040 || all params: 8,072,204,288 || trainable%: 0.5196
None
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3 id="Prapare-data-for-model-feed">Prapare data for model feed<a class="anchor-link" href="#Prapare-data-for-model-feed">¶</a></h3>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;"> Now its time to design format prompt for mental health analysis. This function analyzes the input text from a psychological perspective, identifying indicators of emotional distress, coping mechanisms, or overall mental well-being. It also highlights potential concerns or positive aspects, providing brief explanations for each observation. We are going to prepare this data for further processing by the model, ensuring that each input-output pair is clearly formatted for effective analysis.
</div>
<h3 style="color: #388e3c; font-family: Arial, sans-serif;">Main points to remember:</h3>
<ol style="margin-left: 20px;">
<li><strong>Data Prompt Structure:</strong>
<p>The <code>data_prompt</code> is a formatted string template designed to guide the model in analyzing the provided text. It includes placeholders for the input text (the context) and the model's response. This template specifically prompts the model to identify mental health indicators, making it easier to fine-tune the model for mental health-related tasks.</p>
</li>
<li><strong>End-of-Sequence Token:</strong>
<p>The <code>EOS_TOKEN</code> is retrieved from the tokenizer to signify the end of each text sequence. This token is essential for the model to recognize when a prompt has ended, helping to maintain the structure of the data during training or inference.</p>
</li>
<li><strong>Formatting Function:</strong>
<p>The <code>formatting_prompt</code> used to take a batch of examples and formats them according to the <code>data_prompt</code>. It iterates over the input and output pairs, inserting them into the template and appending the EOS token at the end. The function then returns a dictionary containing the formatted text, ready for model training or evaluation.</p>
</li>
<li><strong>Function Output:</strong>
<p>The function outputs a dictionary where the key is <code>"text"</code> and the value is a list of formatted strings. Each string represents a fully prepared prompt for the model, combining the context, response and the structured prompt template.</p>
</li>
</ol>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">data_prompt</span> <span class="o">=</span> <span class="s2">"""Analyze the provided text from a mental health perspective. Identify any indicators of emotional distress, coping mechanisms, or psychological well-being. Highlight any potential concerns or positive aspects related to mental health, and provide a brief explanation for each observation.</span>

<span class="s2">### Input:</span>
<span class="si">{}</span>

<span class="s2">### Response:</span>
<span class="si">{}</span><span class="s2">"""</span>

<span class="n">EOS_TOKEN</span> <span class="o">=</span> <span class="n">tokenizer</span><span class="o">.</span><span class="n">eos_token</span>
<span class="k">def</span> <span class="nf">formatting_prompt</span><span class="p">(</span><span class="n">examples</span><span class="p">):</span>
    <span class="n">inputs</span>       <span class="o">=</span> <span class="n">examples</span><span class="p">[</span><span class="s2">"Context"</span><span class="p">]</span>
    <span class="n">outputs</span>      <span class="o">=</span> <span class="n">examples</span><span class="p">[</span><span class="s2">"Response"</span><span class="p">]</span>
    <span class="n">texts</span> <span class="o">=</span> <span class="p">[]</span>
    <span class="k">for</span> <span class="n">input_</span><span class="p">,</span> <span class="n">output</span> <span class="ow">in</span> <span class="nb">zip</span><span class="p">(</span><span class="n">inputs</span><span class="p">,</span> <span class="n">outputs</span><span class="p">):</span>
        <span class="n">text</span> <span class="o">=</span> <span class="n">data_prompt</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">input_</span><span class="p">,</span> <span class="n">output</span><span class="p">)</span> <span class="o">+</span> <span class="n">EOS_TOKEN</span>
        <span class="n">texts</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">text</span><span class="p">)</span>
    <span class="k">return</span> <span class="p">{</span> <span class="s2">"text"</span> <span class="p">:</span> <span class="n">texts</span><span class="p">,</span> <span class="p">}</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3 id="Format-the-data-for-training">Format the data for training<a class="anchor-link" href="#Format-the-data-for-training">¶</a></h3>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">training_data</span> <span class="o">=</span> <span class="n">Dataset</span><span class="o">.</span><span class="n">from_pandas</span><span class="p">(</span><span class="n">filtered_data</span><span class="p">)</span>
<span class="n">training_data</span> <span class="o">=</span> <span class="n">training_data</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">formatting_prompt</span><span class="p">,</span> <span class="n">batched</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3 id="Model-training-with-custom-parameters-and-data">Model training with custom parameters and data<a class="anchor-link" href="#Model-training-with-custom-parameters-and-data">¶</a></h3>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<blockquote>
<p style="font-size: 14px; color: #333;">
</p></blockquote>
<pre><code>    Using &lt;code&gt;sudo apt-get update&lt;/code&gt; to refresh the list of available packages and &lt;code&gt;sudo apt-get install build-essential&lt;/code&gt; to install essential tools. Only run this on shell if you get any error.
&lt;/p&gt;
</code></pre>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#sudo apt-get update</span>
<span class="c1">#sudo apt-get install build-essential</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3 style="color: #388e3c; font-family: Arial, sans-serif;">Training setup to start fine tuning!</h3>
<ol style="margin-left: 20px;">
<li><strong>Trainer Initialization:</strong>
<p>We are going to initialize <code>SFTTrainer</code> with the model and tokenizer, as well as the training dataset. The <code>dataset_text_field</code> parameter specifies the field in the dataset that contains the text to be used for training which we prepared above. The trainer is responsible for managing the fine-tuning process, including data handling and model updates.</p>
</li>
<li><strong>Training Arguments:</strong>
<p>The <code>TrainingArguments</code> class is used to define key hyperparameters for the training process. These include:</p>
<ul>
<li><code>learning_rate=3e-4</code>: Sets the learning rate for the optimizer.</li>
<li><code>per_device_train_batch_size=32</code>: Defines the batch size per device, optimizing GPU usage.</li>
<li><code>num_train_epochs=20</code>: Specifies the number of training epochs.</li>
<li><code>fp16=not is_bfloat16_supported()</code> and <code>bf16=is_bfloat16_supported()</code>: Enable mixed precision training to reduce memory usage, depending on hardware support.</li>
<li><code>optim="adamw_8bit"</code>: Uses the 8-bit AdamW optimizer for efficient memory usage.</li>
<li><code>weight_decay=0.01</code>: Applies weight decay to prevent overfitting.</li>
<li><code>output_dir="output"</code>: Specifies the directory where the trained model and logs will be saved.</li>
</ul>
</li>
<li><strong>Training Process:</strong>
<p>Finally we called <code>trainer.train()</code> method to start the training process. It uses the defined parameters of our fine-tune the model, adjusting weights and learning from the provided dataset. The trainer also handles data packing and gradient accumulation, optimizing the training pipeline for better performance.</p>
</li>
</ol>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">trainer</span><span class="o">=</span><span class="n">SFTTrainer</span><span class="p">(</span>
    <span class="n">model</span><span class="o">=</span><span class="n">model</span><span class="p">,</span>
    <span class="n">tokenizer</span><span class="o">=</span><span class="n">tokenizer</span><span class="p">,</span>
    <span class="n">train_dataset</span><span class="o">=</span><span class="n">training_data</span><span class="p">,</span>
    <span class="n">dataset_text_field</span><span class="o">=</span><span class="s2">"text"</span><span class="p">,</span>
    <span class="n">max_seq_length</span><span class="o">=</span><span class="n">max_seq_length</span><span class="p">,</span>
    <span class="n">dataset_num_proc</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span>
    <span class="n">packing</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
    <span class="n">args</span><span class="o">=</span><span class="n">TrainingArguments</span><span class="p">(</span>
        <span class="n">learning_rate</span><span class="o">=</span><span class="mf">3e-4</span><span class="p">,</span>
        <span class="n">lr_scheduler_type</span><span class="o">=</span><span class="s2">"linear"</span><span class="p">,</span>
        <span class="n">per_device_train_batch_size</span><span class="o">=</span><span class="mi">32</span><span class="p">,</span>
        <span class="n">gradient_accumulation_steps</span><span class="o">=</span><span class="mi">4</span><span class="p">,</span>
        <span class="n">num_train_epochs</span><span class="o">=</span><span class="mi">20</span><span class="p">,</span>
        <span class="n">fp16</span><span class="o">=</span><span class="ow">not</span> <span class="n">is_bfloat16_supported</span><span class="p">(),</span>
        <span class="n">bf16</span><span class="o">=</span><span class="n">is_bfloat16_supported</span><span class="p">(),</span>
        <span class="n">logging_steps</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">optim</span><span class="o">=</span><span class="s2">"adamw_8bit"</span><span class="p">,</span>
        <span class="n">weight_decay</span><span class="o">=</span><span class="mf">0.01</span><span class="p">,</span>
        <span class="n">warmup_steps</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span>
        <span class="n">output_dir</span><span class="o">=</span><span class="s2">"output"</span><span class="p">,</span>
        <span class="n">seed</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>
    <span class="p">),</span>
<span class="p">)</span>

<span class="n">trainer</span><span class="o">.</span><span class="n">train</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Generating train split: 0 examples [00:00, ? examples/s]</pre>
</div>
</div>
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr" tabindex="0">
<pre>==((====))==  Unsloth - 2x faster free finetuning | Num GPUs = 1
   \\   /|    Num examples = 593 | Num Epochs = 20
O^O/ \_/ \    Batch size per device = 32 | Gradient Accumulation steps = 4
\        /    Total batch size = 128 | Total steps = 80
 "-____-"     Number of trainable parameters = 41,943,040
</pre>
</div>
</div>
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output" data-mime-type="text/html" tabindex="0">
<div>
<progress max="80" style="width:300px; height:20px; vertical-align: middle;" value="80"></progress>
      [80/80 49:24, Epoch 16/20]
    </div>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: left;">
<th>Step</th>
<th>Training Loss</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>2.337100</td>
</tr>
<tr>
<td>2</td>
<td>2.130900</td>
</tr>
<tr>
<td>3</td>
<td>2.112800</td>
</tr>
<tr>
<td>4</td>
<td>2.045100</td>
</tr>
<tr>
<td>5</td>
<td>2.048000</td>
</tr>
<tr>
<td>6</td>
<td>1.936200</td>
</tr>
<tr>
<td>7</td>
<td>2.096400</td>
</tr>
<tr>
<td>8</td>
<td>1.974700</td>
</tr>
<tr>
<td>9</td>
<td>1.904400</td>
</tr>
<tr>
<td>10</td>
<td>1.892900</td>
</tr>
<tr>
<td>11</td>
<td>1.982600</td>
</tr>
<tr>
<td>12</td>
<td>1.873400</td>
</tr>
<tr>
<td>13</td>
<td>1.815600</td>
</tr>
<tr>
<td>14</td>
<td>1.935400</td>
</tr>
<tr>
<td>15</td>
<td>1.713600</td>
</tr>
<tr>
<td>16</td>
<td>1.866900</td>
</tr>
<tr>
<td>17</td>
<td>1.871300</td>
</tr>
<tr>
<td>18</td>
<td>1.920500</td>
</tr>
<tr>
<td>19</td>
<td>1.808900</td>
</tr>
<tr>
<td>20</td>
<td>1.835500</td>
</tr>
<tr>
<td>21</td>
<td>1.857000</td>
</tr>
<tr>
<td>22</td>
<td>1.751200</td>
</tr>
<tr>
<td>23</td>
<td>1.639800</td>
</tr>
<tr>
<td>24</td>
<td>1.775700</td>
</tr>
<tr>
<td>25</td>
<td>1.763900</td>
</tr>
<tr>
<td>26</td>
<td>1.620300</td>
</tr>
<tr>
<td>27</td>
<td>1.815400</td>
</tr>
<tr>
<td>28</td>
<td>1.750500</td>
</tr>
<tr>
<td>29</td>
<td>1.632600</td>
</tr>
<tr>
<td>30</td>
<td>1.647700</td>
</tr>
<tr>
<td>31</td>
<td>1.592000</td>
</tr>
<tr>
<td>32</td>
<td>1.722700</td>
</tr>
<tr>
<td>33</td>
<td>1.624000</td>
</tr>
<tr>
<td>34</td>
<td>1.548300</td>
</tr>
<tr>
<td>35</td>
<td>1.552900</td>
</tr>
<tr>
<td>36</td>
<td>1.566300</td>
</tr>
<tr>
<td>37</td>
<td>1.538400</td>
</tr>
<tr>
<td>38</td>
<td>1.443100</td>
</tr>
<tr>
<td>39</td>
<td>1.547300</td>
</tr>
<tr>
<td>40</td>
<td>1.412400</td>
</tr>
<tr>
<td>41</td>
<td>1.420000</td>
</tr>
<tr>
<td>42</td>
<td>1.438600</td>
</tr>
<tr>
<td>43</td>
<td>1.321900</td>
</tr>
<tr>
<td>44</td>
<td>1.395400</td>
</tr>
<tr>
<td>45</td>
<td>1.309600</td>
</tr>
<tr>
<td>46</td>
<td>1.277700</td>
</tr>
<tr>
<td>47</td>
<td>1.429000</td>
</tr>
<tr>
<td>48</td>
<td>1.233900</td>
</tr>
<tr>
<td>49</td>
<td>1.283100</td>
</tr>
<tr>
<td>50</td>
<td>1.298300</td>
</tr>
<tr>
<td>51</td>
<td>1.244600</td>
</tr>
<tr>
<td>52</td>
<td>1.079900</td>
</tr>
<tr>
<td>53</td>
<td>1.246000</td>
</tr>
<tr>
<td>54</td>
<td>1.182800</td>
</tr>
<tr>
<td>55</td>
<td>1.079700</td>
</tr>
<tr>
<td>56</td>
<td>1.169200</td>
</tr>
<tr>
<td>57</td>
<td>0.931700</td>
</tr>
<tr>
<td>58</td>
<td>1.108200</td>
</tr>
<tr>
<td>59</td>
<td>0.995700</td>
</tr>
<tr>
<td>60</td>
<td>1.095500</td>
</tr>
<tr>
<td>61</td>
<td>0.895800</td>
</tr>
<tr>
<td>62</td>
<td>1.023300</td>
</tr>
<tr>
<td>63</td>
<td>0.906100</td>
</tr>
<tr>
<td>64</td>
<td>1.010400</td>
</tr>
<tr>
<td>65</td>
<td>0.989300</td>
</tr>
<tr>
<td>66</td>
<td>0.957600</td>
</tr>
<tr>
<td>67</td>
<td>0.870900</td>
</tr>
<tr>
<td>68</td>
<td>0.864400</td>
</tr>
<tr>
<td>69</td>
<td>1.031500</td>
</tr>
<tr>
<td>70</td>
<td>0.963500</td>
</tr>
<tr>
<td>71</td>
<td>0.780400</td>
</tr>
<tr>
<td>72</td>
<td>0.840600</td>
</tr>
<tr>
<td>73</td>
<td>0.855200</td>
</tr>
<tr>
<td>74</td>
<td>0.873100</td>
</tr>
<tr>
<td>75</td>
<td>0.864400</td>
</tr>
<tr>
<td>76</td>
<td>0.774500</td>
</tr>
<tr>
<td>77</td>
<td>0.927100</td>
</tr>
<tr>
<td>78</td>
<td>0.763100</td>
</tr>
<tr>
<td>79</td>
<td>0.774800</td>
</tr>
<tr>
<td>80</td>
<td>0.868500</td>
</tr>
</tbody>
</table><p>
</p></div>
</div>
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[ ]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>TrainOutput(global_step=80, training_loss=1.4284833692014218, metrics={'train_runtime': 3007.0031, 'train_samples_per_second': 3.944, 'train_steps_per_second': 0.027, 'total_flos': 9.2735910445056e+17, 'train_loss': 1.4284833692014218, 'epoch': 16.842105263157894})</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h2 id="Inference">Inference<a class="anchor-link" href="#Inference">¶</a></h2>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">text</span><span class="o">=</span><span class="s2">"I'm going through some things with my feelings and myself. I barely sleep and I do nothing but think about how I'm worthless and how I shouldn't be here. I've never tried or contemplated suicide. I've always wanted to fix my issues, but I never get around to it. How can I change my feeling of being worthless to everyone?"</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;">
<strong>Note:</strong> Lets use the fine-tuned model for inference in order to generate responses based on mental health-related prompts !
</div>
<h3 style="color: #388e3c; font-family: Arial, sans-serif;">Here is some keys to note:</h3>
<ol style="margin-left: 20px;">
<p>The <code>model = FastLanguageModel.for_inference(model)</code> configures the model specifically for inference, optimizing its performance for generating responses.</p>

<p>The input text is tokenized using the <code>tokenizer</code>, it convert the text into a format that model can process. We are using <code>data_prompt</code> to format the input text, while the response placeholder is left empty to get response from model. The <code>return_tensors = "pt"</code> parameter specifies that the output should be in PyTorch tensors, which are then moved to the GPU using <code>.to("cuda")</code> for faster processing.</p>

<p>The <code>model.generate</code> method generating response based on the tokenized inputs. The parameters <code>max_new_tokens = 5020</code> and <code>use_cache = True</code> ensure that the model can produce long and coherent responses efficiently by utilizing cached computation from previous layers.</p>

</ol>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">model</span> <span class="o">=</span> <span class="n">FastLanguageModel</span><span class="o">.</span><span class="n">for_inference</span><span class="p">(</span><span class="n">model</span><span class="p">)</span>
<span class="n">inputs</span> <span class="o">=</span> <span class="n">tokenizer</span><span class="p">(</span>
<span class="p">[</span>
    <span class="n">data_prompt</span><span class="o">.</span><span class="n">format</span><span class="p">(</span>
        <span class="c1">#instructions</span>
        <span class="n">text</span><span class="p">,</span>
        <span class="c1">#answer</span>
        <span class="s2">""</span><span class="p">,</span>
    <span class="p">)</span>
<span class="p">],</span> <span class="n">return_tensors</span> <span class="o">=</span> <span class="s2">"pt"</span><span class="p">)</span><span class="o">.</span><span class="n">to</span><span class="p">(</span><span class="s2">"cuda"</span><span class="p">)</span>

<span class="n">outputs</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">generate</span><span class="p">(</span><span class="o">**</span><span class="n">inputs</span><span class="p">,</span> <span class="n">max_new_tokens</span> <span class="o">=</span> <span class="mi">5020</span><span class="p">,</span> <span class="n">use_cache</span> <span class="o">=</span> <span class="kc">True</span><span class="p">)</span>
<span class="n">answer</span><span class="o">=</span><span class="n">tokenizer</span><span class="o">.</span><span class="n">batch_decode</span><span class="p">(</span><span class="n">outputs</span><span class="p">)</span>
<span class="n">answer</span> <span class="o">=</span> <span class="n">answer</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span><span class="o">.</span><span class="n">split</span><span class="p">(</span><span class="s2">"### Response:"</span><span class="p">)[</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"Answer of the question is:"</span><span class="p">,</span> <span class="n">answer</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Answer of the question is: 
Hi there, I want to acknowledge you for reaching out to ask for help. That's the first step! It sounds like you are experiencing some depression symptoms and it is important to seek help for them as they can worsen over time. You are not worthless and this thought is only a thought, it's not the truth. A professional counsellor can help you change negative thought patterns, build coping skills and learn to challenge negative thoughts. I recommend you to contact a professional counsellor, your family doctor or a crisis hot-line to discuss your symptoms. You are not alone and you can get help! Take care. Rosanne Bermudez, CCVP, RCCWS &lt;|im_end|&gt;
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;"> <strong>Note:</strong> Here is how we can securely push a fine-tuned model and its tokenizer to the Hugging Face Hub so any body can use it. It can be accessed on my account <strong><a href="https://huggingface.co/ImranzamanML/finetuned_llama3.1" target="_blank">ImranzamanML/finetuned_llama3.1</a></strong>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">os</span><span class="o">.</span><span class="n">environ</span><span class="p">[</span><span class="s2">"HF_TOKEN"</span><span class="p">]</span> <span class="o">=</span> <span class="s2">"hugging face token key, you can create from your HF account."</span>
<span class="n">model</span><span class="o">.</span><span class="n">push_to_hub</span><span class="p">(</span><span class="s2">"ImranzamanML/finetuned_llama3.1"</span><span class="p">,</span> <span class="n">use_auth_token</span><span class="o">=</span><span class="n">os</span><span class="o">.</span><span class="n">getenv</span><span class="p">(</span><span class="s2">"HF_TOKEN"</span><span class="p">))</span>
<span class="n">tokenizer</span><span class="o">.</span><span class="n">push_to_hub</span><span class="p">(</span><span class="s2">"ImranzamanML/finetuned_llama3.1"</span><span class="p">,</span> <span class="n">use_auth_token</span><span class="o">=</span><span class="n">os</span><span class="o">.</span><span class="n">getenv</span><span class="p">(</span><span class="s2">"HF_TOKEN"</span><span class="p">))</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>README.md:   0%|          | 0.00/31.0 [00:00&lt;?, ?B/s]</pre>
</div>
</div>
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>adapter_model.safetensors:   0%|          | 0.00/168M [00:00&lt;?, ?B/s]</pre>
</div>
</div>
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Saved model to https://huggingface.co/ImranzamanML/finetuned_llama3.1
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;"> <strong>Note:</strong> We can also save fine-tuned model and its tokenizer locally on the machine.
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">model</span><span class="o">.</span><span class="n">save_pretrained</span><span class="p">(</span><span class="s2">"model/finetuned_llama3.1"</span><span class="p">)</span>
<span class="n">tokenizer</span><span class="o">.</span><span class="n">save_pretrained</span><span class="p">(</span><span class="s2">"model/finetuned_llama3.1"</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;"> Still 👀 for something?
</div>
Ok let me show you how you can load your saved model and use it!
<pre style="background-color: #e0f7fa; border: 1px solid #009688; padding: 10px; border-radius: 5px; font-family: Consolas, 'Courier New', monospace; font-size: 14px;">
model, tokenizer = FastLanguageModel.from_pretrained(
model_name = "model/finetuned_llama3.1",
max_seq_length = 5020,
dtype = None,
load_in_4bit = True)
</pre>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p style="font-family: Comic Sans MS, cursive, sans-serif; color: #333; font-size: 16px;">
    No way, still searching for something? 😄 No worries! You can use the prompt format and code above to get response for mental peace 🧠✨
</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Happy-to-Connect-%F0%9F%98%8A">Happy to Connect 😊<a class="anchor-link" href="#Happy-to-Connect-%F0%9F%98%8A">¶</a></h4><div style="background-color: #f9f9f9; border: 1px solid #ddd; padding: 20px; text-align: center; font-family: Arial, sans-serif;">
<h3 style="margin-bottom: 20px;">Muhammad Imran Zaman</h3>
<a href="https://www.kaggle.com/muhammadimran112233" style="text-decoration: none; margin-right: 20px;">
<img alt="Kaggle Profile" height="100" src="https://www.kaggle.com/static/images/site-logo.svg" width="100"/>
</a>
<a href="https://www.linkedin.com/in/muhammad-imran-zaman" style="text-decoration: none; margin-right: 20px;">
<img alt="LinkedIn Profile" height="50" src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/LinkedIn_logo_initials.png/600px-LinkedIn_logo_initials.png" width="50"/>
</a>
<a href="https://scholar.google.com/citations?user=ulVFpy8AAAAJ&amp;hl=en" style="text-decoration: none; margin-right: 20px;">
<img alt="Google Scholar Profile" height="50" src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c7/Google_Scholar_logo.svg/768px-Google_Scholar_logo.svg.png" width="50"/>
</a>
<a href="https://www.youtube.com/@consolioo" style="text-decoration: none; margin-right: 20px;">
<img alt="YouTube Channel" height="50" src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/72/YouTube_social_white_square_%282017%29.svg/640px-YouTube_social_white_square_%282017%29.svg.png" width="50"/>
</a>
<a href="https://github.com/Imran-ml" style="text-decoration: none; margin-right: 20px;">
<img alt="GitHub Profile" height="50" src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="50"/>
</a>
<a href="https://imranzaman-5202.medium.com/" style="text-decoration: none; margin-right: 20px;">
<img alt="Medium Profile" height="50" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAeFBMVEUAAAD///+3t7f8/Pzs7Oz39/d6enpPT0/IyMjy8vL19fWtra04ODhxcXHU1NSqqqpeXl6Xl5fc3NwJCQl/f38WFhbm5uaPj4/AwMArKyuFhYVNTU1kZGQREREyMjJFRUUiIiKgoKBoaGgnJyc9PT2MjIwcHBxWVlbgTdlVAAAEsUlEQVR4nO3c6XqqMBAGYHDD3dbj1rpUu9j7v8NTCAhhnYQZofZ7f/LEmGHJRoLjAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQJtdp95hNpsd9qdj00Xh9zHoLEdubDSfDP41XSg+h04yuFhv4TVdNA6nST83vDDIy9Usu9VuMx7NF98yhbVwmJeEp+zeyLkdO/GpWQmWmm6/rIzPNzzRsltpv1qeRctOsR6S4vNNKPl10r96ko6gwis5vh/jQ2V+Off7IC/ddL67T2NU/QDqOhX55d4QOVfx2nXdjUhEOq+sAs3XeynLcJL/o2kmYXAmLmKBRQbG8flKmoD3otOSTngKDnclg/NdrAIseK5868KfpG/u8Fq/yga4sAzQdYsauZJaOdUtGqujc9EAL9YBFl3Fp5Jf6LWKFx1eCwb4XCNA133Py3JT9gvthrzdPoU3fH2zWgG6bk4frjzLfjLprRNV1fjY+6wZoF5gpfQS6g/v7WCmkmWTP04ykakkyp5CX+JJ9OKjUqPPTN/RwnMqz8rubdyObuODQp3WqtNNo3duitvCyC7vBKfPExPzvlqepZbntvoHt7SJ0ZpMVXNhCTBV1VfUM1r6xBleZotX35UpQK0+fSGkH0aJE8dGEhFyVDNK4iH6IiSPOtpe8qBAgGyXULuIpImCsOLUhjSf/BEWDOGsxF2xLiX5QqXVOowz/ghJZSG6dUneSMnDakV7TL7YA1wV/b2VaFBEaCt8KrF2R/OP800nZspFzdmOllydEG3ycldcVDvVXQ8jUV3ToyVXz63WKR4Wl9WO0eQhQXibEh9uNeGqdanYm3z69C+Nqh6pg7F59nSwj5/GzBGqS1A0x5YWhHPWDnHPt52YAwyrR/KUiJ94Khohb1vhCx5E8rTd2cm0ncwRcnZolKB6JD/deyfVLWWfbuOuaMLqkfZ6zlUDqNT4u/QtgTnCKM7Q0Chb/4of9EPMXW/OTqkSTDCRJ7a2TmbWkf5uuaEIe0bZ+r3Q1PugPWuA5/z/rSMYpJNTL6QjpMw1GOrXjZB3KYtAhN2Hj7Bl1/Dxn0N6UchaVpf+gfawDX2a1FAru06jlqb7pf7coWy/1H51QhGzsYVfccqOLfjHh99GJ+7sSI8P+RvEINsWjfEff56m4bk2dT5k59q450vDl/Mtmi9tds5bvYaRnfNu9r2F6qHJvrf4A++e2vb+UGAB5uO/A2YcI3K8x2fueAf41mJs40zbtBaD7yK2dj2Nc2GKsLVromTWtRE637e04uva0m8OLOnboI6V6XPXJm7TZWPSyPrSeCmp/PpScj+yBNMaYakAU6NQC61f500esxYxXquvNQt3WKt///0W2j6bS3RUcL9FS/bMyG5BtA+Rbd+TUHt/Y3uj/pq9a7Zbgzj2H4Z1uWRwyv7R95A6ze0DPt5pH7BjOL3Yt9rLnTuMn86H9/rixpE4T+b+1v34PzzRbyp8yBae6Jv1uxjXxHcxRDstRk6Tsnc2I9Nvm7zuNv3RvG2ffXkq+j7NpGUFreO8euhvDEXWU+89+E7U9AG/EwUAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAJ/wFTZUNtMEP4sAAAAABJRU5ErkJggg==" width="50"/>
</a>
<a href="https://huggingface.co/ImranzamanML" style="text-decoration: none;">
<img alt="Hugging Face Profile" height="100" src="https://huggingface.co/datasets/huggingface/brand-assets/resolve/main/hf-logo-with-title.svg" width="200"/>
</a>
</div>
</div>
</div>
</div>
</div>
</main>
</body>
</html>

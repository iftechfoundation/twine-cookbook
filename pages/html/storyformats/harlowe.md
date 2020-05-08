# Harlowe HTML

Harlowe uses a variety of HTML elements and attributes to organize its stories.

The following are snapshots of HTML element differences between major versions in Harlowe.

## Harlowe 1.X

```html
<tw-story>
  <tw-passage>
    <tw-sidebar>
    <tw-icon tabindex="0" class="undo" title="Undo" style="visibility: hidden;">↶</tw-icon>
    <tw-icon tabindex="0" class="redo" title="Redo" style="visibility: hidden;">↷</tw-icon>
    </tw-sidebar>
    <tw-expression type="macro" name="link-goto">
      <tw-link tabindex="0" passage-name="Another" data-raw="">Another</tw-link>
    </tw-expression>
  </tw-passage>
</tw-story>
```

## Harlowe 2.X

```html
<tw-story tags="">
  <tw-passage tags="">
  <tw-sidebar>
    <tw-icon tabindex="0" class="undo" title="Undo" style="visibility: hidden;">↶</tw-icon>
    <tw-icon tabindex="0" class="redo" title="Redo" style="visibility: hidden;">↷</tw-icon>
  </tw-sidebar>
  <tw-expression type="macro" name="link-goto">
    <tw-link tabindex="0" passage-name="Another" data-raw="">Another</tw-link>
  </tw-expression>
  </tw-passage>
</tw-story>
```

## Harlowe 3.X

```html
<tw-story tags="">
  <tw-passage tags="">
    <tw-sidebar>
      <tw-icon tabindex="0" class="undo" title="Undo" style="visibility: hidden;">↶</tw-icon>
      <tw-icon tabindex="0" class="redo" title="Redo" style="visibility: hidden;">↷</tw-icon>
   </tw-sidebar>
   <tw-expression type="macro" name="link-goto">
     <tw-link tabindex="0" data-raw="">Another</tw-link>
   </tw-expression>
  </tw-passage>
</tw-story>
```

# Harlowe HTML

## Harlowe 1.X HTML

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

## Harlowe 2.X HTML

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

## Harlowe 3.X HTML

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

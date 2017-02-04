# Relative assets and `moduleId`

Since Angular2, we can now reference a component's view's assets, i.e. `html` and `css` using relative assets metadata e.g.
`templateUrl` and `styleUrls`.

What this means is that instead of us having to specify the location of these assets from the root/base folder of the app, we can just conveniently identify their location relative to where their corresponding component lies.

```ts
// Assume this component and its class lies in some `app/components/test.component.ts`
@Component({
  moduleId: module.id,
  selector: 'my-test-app'
  templateUrl: 'test.component.html',
  styleUrls: ['test.component.css'] // expects an array as you could have multiple...
})
```

This cool feature is actually made possible by another **important** metadata property, `moduleId`.

`moduleId` allows Angular to identify the source/base address of a component, thereby being able to support module-relative URLs/paths.

_note: There are some bundling tools for Angular, e.g. webpack, that does the setting of `moduleId` for you behind the scenes._





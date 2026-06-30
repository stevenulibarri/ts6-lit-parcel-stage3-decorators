# ts6-lit-parcel-stage3-decorators

Working sample setup using typescript, lit, and parcel with stage 3 decorators.  
Saving it for later.  

lit needs:  
```json
"experimentalDecorators": false,
"useDefineForClassFields": true,
```
for stage 3 decorators.  

Then force parcel to use tsc instead of swc in `.parcelrc`:
```json
{
  "extends": "@parcel/config-default",
  "transformers": {
    "*.{ts,tsx}": [
      "@parcel/transformer-typescript-tsc"
    ]
  }
}
```

tangent but if using a ui library like `flatpickr` and you need to import its css via node_modules so parcel can find it you just need
```ts
declare module '*.css' {
  const content: string;
  export default content;
}
```
in `global.d.ts`.

`npm run dev` to run dev server  
`npm run build` to build  


---
title: Avatar Component
_description: Ignite UI for Angular Avatar control enables users to add images, material icons or initials within any application for instances such as a profile button. 
_keywords: Ignite UI for Angular, UI controls, Angular widgets, web widgets, UI widgets, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components Library, Angular Avatar component, Angular Avatar control
---

##Avatar

The **igx-avatar** component allows you to add images or initials as avatars in your application.

### Usage
```html
<igx-avatar roundShape="true" icon="person" bgColor="#0375be" data-init="SS">
</igx-avatar>
```

### API Summary
| Name   |      Type      |  Description |
|:----------|:-------------:|:------|
| `src` |  string | Set the image source of the avatar. |
| `initials` | string | Set the initials of the avatar. |
| `icon` | string | Set the icon of the avatar. Currently all icons from the material icon set are supported. Not applicable for initials and image avatars. |
| `bgColor` | string | Set the background color of initials or icon avatars. |
| `color` | string | Set the color of initials or icon avatars. (optional) |
| `roundShape` | boolean | Set the shape of the avatar to circle. The default shape is square. |
| `size` | string | Set the size of the avatar to either small, medium, or large. |

*You can also set all igx-avatar properties programmatically.

### Examples

Using `igx-avatar` tag to include it into your app.
```html
<igx-avatar roundShape="true" icon="person" bgColor="#0375be" data-init="SS">
</igx-avatar>
```

Using `TypeScript` to modify and existing igx-avatar instance.
```typescript
avatarInstance.srcImage('https://unsplash.it/60/60?image=55');
avatarInstance.size('small');
```
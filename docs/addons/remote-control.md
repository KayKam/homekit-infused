# Homekit Infused 5

## Content
- [Introduction](../index.md)
- [Installation](../installation.md)
- [Configuration](../configuration.md)
- [Addons](../addons.md)
- [Updates](../updates.md)
- [Issues & Questions](../issues.md)
- [About Me](../about.md)
- [Thanks](../thanks.md)

## Addons > Remote Control

This addon gives your view a remote control that is suitable for Android TV, it also works for Apple TV's though not all features are working yet.

You can use any of the following options to modify your addon.

### Stack and Addon Config

| Name | Required | Default | Description |
|----------------------------------|-------------|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| title | no | undefined | Set the title of the stack, ommitting this line will or setting `title: hide` will hide the title |
| media_player | yes | undefined | Set your media_player entity here, usually this is something like `media_player.shield_tv` or `media_player.kitchen_apple_tv` |
| sound_player | yes | undefined | If you have a separate sound player you can enter the entity here, else use the same entity as the media_player |
| remote_entity | yes | undefined | Set your entity that is used as the remote control (for Android TV you must use the same entity as the media_player) |
| type | no | undefined | Set to `atv` if you have an Apple TV, otherwise don't use this line |
| [view_layout](layout.md#view-layout) | no | undefined | This is best used in conjunction with the [layout](layout.md#view-layout) addon, but can also be used to control whether to show this stack on different screen sizes. |
| conditional | no | false | Setting this to `true` will make the stack condtional |
| conditions | no | undefined | Add entities and conditions, this will determine when this addon will be shown, e.g. if entity x is turned `on`, then show this addon (see [addons](../addons.md) for examples |

```yaml
# views.yaml (example shield tv)
  my_view:
    addons:
      remote_control:
        - title: Livingroom
          media_player: media_player.nvidia_shield
          sound_player: media_player.nvidia_shield
          remote_entity: media_player.nvidia_shield
```   
```yaml
# views.yaml (example apple tv)
  my_view:
    addons:
      remote_control:
        - title: Bedroom
          media_player: media_player.apple_tv
          sound_player: media_player.apple_tv
          remote_entity: remote.apple_tv
          type: atv
```  
```yaml
# views.yaml (example Android and ATV remote on the same view)
  my_view:
    addons:
      remote_control:
        - title: Livingroom
          media_player: media_player.nvidia_shield
          sound_player: media_player.nvidia_shield
          remote_entity: media_player.nvidia_shield
        - title: Bedroom
          media_player: media_player.apple_tv
          sound_player: media_player.apple_tv
          remote_entity: remote.apple_tv
          type: atv
```  

### Images:

![Homekit Infused](../images/hki-remote-control.png)

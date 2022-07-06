# contextmenu

[![Gitlab pipeline status](https://img.shields.io/gitlab/pipeline/TheOneWithTheBraid/contextmenu/main?label=GitLab%20CI&logo=gitlab&style=flat-square)](https://gitlab.com/TheOneWithTheBraid/contextmenu) [![Pub Version](https://img.shields.io/pub/v/contextmenu?label=Published&logo=flutter&style=flat-square)](https://pub.dev/packages/contextmenu)

Display a beautiful material context menu using pure Flutter.

It works both on touch devices and on desktop devices.

***See a demo [here](https://theonewiththebraid.gitlab.io/contextmenu/)!***

[![Demo Screen Recording](https://gitlab.com/TheOneWithTheBraid/contextmenu/-/raw/main/example/demo.webp?inline=false)](https://gitlab.com/TheOneWithTheBraid/contextmenu/-/raw/main/example/demo.webp?inline=false)

## Features

* modern, emphasizing animation according to material design guidelines
* handles screen edges and oversize
* very efficient code (< 250 lines)

## Getting Started

You can easily display a context menu using the following code:

```dart
Widget build() {
  return ContextMenuArea(
    builder: (context) => [
      ListTile(
        title: Text('Option 1'),
        onTap: () {
          Navigator.of(context).pop();
          ScaffoldMessenger.of(context)
              .showSnackBar(SnackBar(content: Text('Whatever')));
        },
      )
    ],
    child: Card(
      color: Theme
          .of(context)
          .primaryColor,
      child: Center(
        child: Text('Press somewhere for context menu.'),
      ),
    ),
  );
}
```

A more complicated way manually triggering a context menu using `showContextMenu()` is:

```dart
Widget build() {
  return GestureDetector(
      onSecondaryTapDown: (details) =>
          showContextMenu(
              details.globalPosition, context, items, verticalPadding, width),
      child: Text('Tap!'));
}
```

## Setup web

For the web, edit your `index.html` and add the following in the `<body>` tag:

```html

<body oncontextmenu="return false;">
```

## License

This project is EUPL licensed. For further details, consult [LICENSE](LICENSE).

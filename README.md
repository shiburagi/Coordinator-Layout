# coordinator_layout

[![pub package](https://img.shields.io/pub/v/drawerbehavior.svg)](https://pub.dartlang.org/packages/coordinator_layout)

a Library contains widget/layout to handle collapsing header behavior

![Alt Text](https://github.com/shiburagi/Coordinator-Layout/blob/preview/gif.gif)


## Example
```dart
CoordinatorLayout(
    maxHeight: 200,
    minHeight: kToolbarHeight + MediaQuery.of(context).padding.top,
    headers: [
        SliverCollapsingHeader(
            builder: (context, offset, diff) {
                return ...;
            },
        ),
    ],
    body: Container(height: null, child: buildBody(context)),
),
```

#### Fit content

```dart
CoordinatorLayout(
    headerMaxHeight: 200,
    headerMinHeight: kToolbarHeight + MediaQuery.of(context).padding.top,
    header:[ 
        Builder(builder: (context) {
            return SliverOverlapAbsorber(
            handle: NestedScrollView.sliverOverlapAbsorberHandleFor(context),
            sliver: SliverSafeArea(
                top: false,
                sliver: SliverCollapsingHeader(
                builder: (context, offset, diff) {
                    return ...;
                },
                ),
            ),
            );
        }),
    ],
    body: Container(height: null, child: buildBody(context)),
),
```
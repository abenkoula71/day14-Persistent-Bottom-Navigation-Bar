# Day14 Persistent Bottom Navigation Bar flutter


A vertical fullscreen scroll implementation that snaps in place, similar to the TikTok app.

# 1-Add the  Persistent Bottom Navigation Bar dependency in your pubspec.yaml file.

```
dependencies:
  persistent_bottom_nav_bar: ^5.0.2
```

# 2-Import the  tiktoklikescroller package in your dart file.

```
import 'package:persistent_bottom_nav_bar/animations/animations.dart';
import 'package:persistent_bottom_nav_bar/models/nav_bar_animation.model.dart';
import 'package:persistent_bottom_nav_bar/models/nav_bar_essentials.model.dart';
import 'package:persistent_bottom_nav_bar/models/nav_bar_padding.model.dart';
import 'package:persistent_bottom_nav_bar/models/neumorphic_properties.widget.dart';
import 'package:persistent_bottom_nav_bar/models/page_route_transitions.model.dart';
import 'package:persistent_bottom_nav_bar/models/persistent_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/models/persistent_bottom_nav_bar_styles.widget.dart';
import 'package:persistent_bottom_nav_bar/models/persistent_bottom_nav_item.widget.dart';
import 'package:persistent_bottom_nav_bar/models/persistent_nav_bar_scaffold.widget.dart';
import 'package:persistent_bottom_nav_bar/models/route_settings.model.dart';
import 'package:persistent_bottom_nav_bar/models/tab_view.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/neumorphic_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/simple_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_10_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_11_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_12_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_13_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_14_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_15_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_16_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_17_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_18_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_19_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_1_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_2_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_3_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_4_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_5_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_6_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_7_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_8_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/nav_bar_styles/style_9_bottom_nav_bar.widget.dart';
import 'package:persistent_bottom_nav_bar/neumorphic_package_by_serge_software/neumorphic_card.dart';
import 'package:persistent_bottom_nav_bar/paint/paint.dart';
import 'package:persistent_bottom_nav_bar/persistent_tab_view.dart';
import 'package:persistent_bottom_nav_bar/persistent_tab_view.widget.dart';
import 'package:persistent_bottom_nav_bar/utils/functions.utils.dart';
import 'package:persistent_bottom_nav_bar/utils/navigator_functions.utils.dart';
```

# 3-use him like this

```
import 'package:flutter/material.dart';
import 'package:tiktoklikescroller/tiktoklikescroller.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final List<Color> colors = <Color>[Colors.red, Colors.blue, Colors.green];
    final Controller controller = Controller()
      ...addListener((event) {
        _handleCallbackEvent(event.direction, event.success);
      });

    return MaterialApp(
      home: Scaffold(
        body: TikTokStyleFullPageScroller(
          contentSize: colors.length,
          swipePositionThreshold: 0.2,
          // ^ the fraction of the screen needed to scroll
          swipeVelocityThreshold: 2000,
          // ^ the velocity threshold for smaller scrolls
          animationDuration: const Duration(milliseconds: 400),
          // ^ how long the animation will take
          controller: controller,
          // ^ registering our own function to listen to page changes
          builder: (BuildContext context, int index) {
            return Container(
                color: colors[index],
                child: Text(
                  '$index',
                  style: const TextStyle(fontSize: 48, color: Colors.white),
                ),
              );
          },
        ),
      ),
    );
  }

  void _handleCallbackEvent(ScrollDirection direction, ScrollSuccess success,
      {int? currentIndex}) {
    print(
        "Scroll callback received with data: {direction: $direction, success: $success and index: ${currentIndex ?? 'not given'}}");
  }

}
```

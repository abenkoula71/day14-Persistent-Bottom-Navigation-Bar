# Day14 Persistent Bottom Navigation Bar flutter


A vertical fullscreen scroll implementation that snaps in place, similar to the TikTok app.

# 1-Add the  Persistent Bottom Navigation Bar dependency in your pubspec.yaml file.

```
dependencies:
  persistent_bottom_nav_bar: ^5.0.2
```

# 2-Import the  tiktoklikescroller package in your dart file.

```
import 'package:persistent_bottom_nav_bar/persistent_tab_view.dart';
```

# 3-use him like this

```
class MyApp extends StatelessWidget {
  const MyApp({Key key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return PersistentTabView(
        context,
        controller: _controller,
        screens: _buildScreens(),
        items: _navBarsItems(),
        confineInSafeArea: true,
        backgroundColor: Colors.white, // Default is Colors.white.
        handleAndroidBackButtonPress: true, // Default is true.
        resizeToAvoidBottomInset: true, // This needs to be true if you want to move up the screen when keyboard appears. Default is true.
        stateManagement: true, // Default is true.
        hideNavigationBarWhenKeyboardShows: true, // Recommended to set 'resizeToAvoidBottomInset' as true while using this argument. Default is true.
        decoration: NavBarDecoration(
          borderRadius: BorderRadius.circular(10.0),
          colorBehindNavBar: Colors.white,
        ),
        popAllScreensOnTapOfSelectedTab: true,
        popActionScreens: PopActionScreensType.all,
        itemAnimationProperties: ItemAnimationProperties( // Navigation Bar's items animation properties.
          duration: Duration(milliseconds: 200),
          curve: Curves.ease,
        ),
        screenTransitionAnimation: ScreenTransitionAnimation( // Screen transition animation on change of selected tab.
          animateTabTransition: true,
          curve: Curves.ease,
          duration: Duration(milliseconds: 200),
        ),
        navBarStyle: NavBarStyle.style1, // Choose the nav bar style with this property.
    );
  }
}
```

```
List<Widget> _buildScreens() {
        return [
          MainScreen(),
          SettingsScreen()
        ];
    }
```



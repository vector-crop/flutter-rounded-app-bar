# flutter-rounded-app-bar
flutter rounded app bar with floating 

##code for making the app bar in main.dart
```
  import 'package:flutter/material.dart';

  void main() {
    runApp(MaterialApp(
      home: HomePage(),
    ));
  }

  class HomePage extends StatelessWidget {
    bool _showRedDot = true;
    @override
    Widget build(BuildContext context) {
      return Container(
        color: Colors.white,
        child: SafeArea(
          child: Scaffold(
            appBar: PreferredSize(
              preferredSize: Size.fromHeight(65.0),
              child: Padding(
                padding: const EdgeInsets.all(8.0),
                child: AppBar(
                  backgroundColor: Colors.white,
                  elevation: 8.0,
                  shape: RoundedRectangleBorder(
                    borderRadius: BorderRadius.circular(20.0),
                  ),
                  title: Text(
                    'Notifications',
                    style: TextStyle(color: Colors.black),
                  ),
                  centerTitle: true,
                  leading: IconButton(
                      onPressed: () {
                        Navigator.pop(context);
                      },
                      icon: Icon(
                        Icons.arrow_back,
                        color: Colors.black,
                      )),
                  actions: [
                    IconButton(
                      icon: Icon(
                        Icons.search,
                        color: Colors.black,
                      ),
                      onPressed: () {},
                    ),
                    Stack(
                      children: [
                        IconButton(
                          icon: Icon(
                            Icons.shopping_cart_outlined,
                            color: Colors.black,
                          ),
                          onPressed: () {},
                        ),
                        if (_showRedDot)
                          Positioned(
                            top: 11,
                            right: 11,
                            child: Container(
                              width: 8,
                              height: 8,
                              decoration: BoxDecoration(
                                color: Colors.red,
                                shape: BoxShape.circle,
                              ),
                            ),
                          ),
                      ],
                    ),
                  ],
                ),
              ),
            ),
            body: Container(),
          ),
        ),
      );
    }
  }
```

# Bottom-Navigation-Floating-Button-Centered-Example

# Demo

![alt text](https://github.com/quicklearner4991/Bottom-Navigation-Floating-Button-Centered-Example/blob/main/example-nav.gif)

# Code

```
import 'package:flutter/material.dart';
import 'package:wodl/utils/WodlColors.dart';
import 'package:wodl/utils/WodlDimens.dart';

class DashboardScreen extends StatefulWidget {
  const DashboardScreen({Key? key}) : super(key: key);

  @override
  _DashboardScreenState createState() => _DashboardScreenState();
}

class _DashboardScreenState extends State<DashboardScreen> {
  int pageIndex = 0;

  final pages = [
    const Page1(),
    const Page2(),
    const Page3(),
  ];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      floatingActionButtonLocation: FloatingActionButtonLocation.centerDocked,
      floatingActionButton: FloatingActionButton(
          backgroundColor: Colors.green,
          elevation: 0,
          shape: StadiumBorder(side: BorderSide(color: Colors.white, width: 4)),
          child: const Icon(
            Icons.add,
            size: 40,
          ),
          onPressed: () {
            setState(() {
              pageIndex = 1;
            });
          }),
      appBar: AppBar(
        title: Text(
          "HOME",
          style: TextStyle(
            color: Theme
                .of(context)
                .primaryColor,
            fontSize: 25,
            fontWeight: FontWeight.w600,
          ),
        ),
        centerTitle: true,
        backgroundColor: Colors.white,
      ),
      body: pages[pageIndex],
      bottomNavigationBar: buildMyNavBar(context),
    );
  }

  BottomAppBar buildMyNavBar(BuildContext context) {
    return BottomAppBar(
        color: Colors.white,
        child: Container(
          height: 70,
          child: Row(
            mainAxisAlignment: MainAxisAlignment.spaceEvenly,
            children: [
              Column(
                children: [
                  IconButton(
                    enableFeedback: false,
                    onPressed: () {
                      setState(() {
                        pageIndex = 0;
                      });
                    },
                    icon: pageIndex == 0
                        ? const Icon(
                      Icons.home_filled,
                      size: 35,
                    )
                        : const Icon(
                      Icons.home_outlined,
                      size: 35,
                    ),
                  ),
                  Text(
                    'Home',
                    style: TextStyle(fontSize: 12,
                        color: pageIndex == 0
                            ? Colors.green
                            : Colors.black),
                  )
                ],
              ),
              Container(
                child: Text(
                  'Scan',
                  style: TextStyle(fontSize: 12,
                      color: pageIndex == 1
                          ? Colors.green
                          : Colors.black),
                ),
                margin: EdgeInsets.fromLTRB(0, 40.0, 0, 0),
              ),
              Column(
                children: [
                  IconButton(
                    enableFeedback: false,
                    onPressed: () {
                      setState(() {
                        pageIndex = 2;
                      });
                    },
                    icon: pageIndex == 2
                        ? const Icon(
                      Icons.person,
                      size: 35,
                    )
                        : const Icon(
                      Icons.person_outline,
                      size: 35,
                    ),
                  ),
                  Text(
                    'Journal',
                    style: TextStyle(fontSize: 12 ,
                        color: pageIndex == 2 ? Colors.green:
                        Colors.black),
                  )
                ],
              ) // The dummy child
              ,
            ],
          ),
        ));
  }
}

class Page1 extends StatelessWidget {
  const Page1({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Container(
      color: const Color(0xffC4DFCB),
      child: Center(
        child: Text(
          "Page number 1",
          style: TextStyle(
            color: Colors.green[900],
            fontSize: 45,
            fontWeight: FontWeight.w500,
          ),
        ),
      ),
    );
  }
}

class Page2 extends StatelessWidget {
  const Page2({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Container(
      color: const Color(0xffC4DFCB),
      child: Center(
        child: Text(
          "Page number 2",
          style: TextStyle(
            color: Colors.green[900],
            fontSize: 45,
            fontWeight: FontWeight.w500,
          ),
        ),
      ),
    );
  }
}

class Page3 extends StatelessWidget {
  const Page3({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Container(
      color: const Color(0xffC4DFCB),
      child: Center(
        child: Text(
          "Page number 3",
          style: TextStyle(
            color: Colors.green[900],
            fontSize: 45,
            fontWeight: FontWeight.w500,
          ),
        ),
      ),
    );
  }
}
```


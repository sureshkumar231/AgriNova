import 'package:flutter/material.dart';
import 'dart:ui';
import 'Community.dart';
import 'Maps.dart';
import 'Profile.dart';

class HomePage extends StatefulWidget {
  const HomePage({super.key});

  @override
  State<HomePage> createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {
  int _selectedIndex = 0;
  late PageController _controller;

  @override
  void initState() {
    super.initState();
    _controller = PageController();
  }

  String _getTitle() {
    switch (_selectedIndex) {
      case 0:
        return 'AgriNova';
      case 1:
        return 'Community';
      case 2:
        return 'MapsView';
      case 3:
        return 'Profile';
      default:
        return 'AgriNova';
    }
  }

  TextStyle _getTitleStyle() {
    switch (_selectedIndex) {
      case 0:
        return TextStyle(
          fontSize: 35,
          fontWeight: FontWeight.bold,
          color: Colors.white, // Change to desired color for Home
        );
      case 1:
        return TextStyle(
          fontSize: 35,
          fontWeight: FontWeight.bold,
          color: Colors.green, // Change to desired color for Community
        );
      case 2:
        return TextStyle(
          fontSize: 35,
          fontWeight: FontWeight.bold,
          color: Colors.black, // Change to desired color for Maps
        );
      case 3:
        return TextStyle(
          fontSize: 35,
          fontWeight: FontWeight.bold,
          color: Colors.pink, // Change to desired color for Profile
        );
      default:
        return TextStyle(
          fontSize: 35,
          fontWeight: FontWeight.bold,
          color: Colors.blue, // Default color
        );
    }
  }

  List<Widget> _getActions() {
    switch (_selectedIndex) {
      case 0: // Home page
        return [
          IconButton(
            icon: Icon(Icons.chat_outlined, size: 35, color: Colors.white),
            onPressed: () {
              // Handle search action
            },
          ),
        ];
      case 1: // Community page
        return [
          IconButton(
            icon: Icon(Icons.notifications_outlined,
                size: 35, color: Colors.green),
            onPressed: () {
              // Handle notifications action
            },
          ),
          IconButton(
            icon: Icon(Icons.chat_outlined, size: 35, color: Colors.green),
            onPressed: () {
              // Handle chat action
            },
          ),
        ];
      case 2: // Maps page
        return [
          IconButton(
            icon:
                Icon(Icons.filter_list_outlined, size: 35, color: Colors.black),
            onPressed: () {
              // Handle filter action
            },
          ),
          IconButton(
            icon: Icon(Icons.layers_outlined, size: 35, color: Colors.black),
            onPressed: () {
              // Handle layers action
            },
          ),
        ];
      case 3: // Profile page
        return [
          IconButton(
            icon: Icon(Icons.edit_outlined, size: 35, color: Colors.pink),
            onPressed: () {
              // Handle edit profile action
            },
          ),
          IconButton(
            icon: Icon(Icons.settings_outlined, size: 35, color: Colors.pink),
            onPressed: () {
              // Handle settings action
            },
          ),
        ];
      default:
        return [];
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      extendBodyBehindAppBar:
          true, // Ensures content extends behind the app bar
      appBar: AppBar(
        title: Text(
          _getTitle(),
          style: _getTitleStyle(), // Apply the style here
        ),
        centerTitle: false, // Aligns the title to the left
        actions: _getActions(), // Dynamic actions based on the selected page
        backgroundColor:
            Colors.transparent, // Set the background to transparent
        elevation: 0, // Remove the shadow
      ),
      body: _getPage(), // Display the selected page
      bottomNavigationBar: BottomNavigationBar(
        backgroundColor: Colors.transparent, // Set the color to transparent
        currentIndex: _selectedIndex,
        onTap: _onItemTapped, // Handle taps on the bottom navigation bar
        selectedItemColor: Colors.green,
        unselectedItemColor: Colors.green.withOpacity(0.6),
        items: [
          BottomNavigationBarItem(
            icon: Icon(Icons.home_outlined, size: 35),
            label: 'Home',
          ),
          BottomNavigationBarItem(
            icon: Icon(Icons.group_outlined, size: 35),
            label: 'Community',
          ),
          BottomNavigationBarItem(
            icon: Icon(Icons.map_outlined, size: 35),
            label: 'Maps',
          ),
          BottomNavigationBarItem(
            icon: Icon(Icons.person_outline, size: 35),
            label: 'Profile',
          ),
        ],
      ),
    );
  }

  void _onItemTapped(int index) {
    setState(() {
      _selectedIndex = index;
    });
  }

  Widget _getPage() {
    switch (_selectedIndex) {
      case 0:
        return _buildHomePage(); // Home page content
      case 1:
        return CommunityPage(); // Community page
      case 2:
        return MapsPage(); // Maps page
      case 3:
        return ProfilePage(); // Profile page
      default:
        return _buildHomePage(); // Default to home page
    }
  }

  Widget _buildHomePage() {
    return Stack(
      children: [
        Positioned.fill(
          child: Image.asset(
            'assets/background.png', // Replace with your image path
            fit: BoxFit.cover,
            errorBuilder: (context, error, stackTrace) {
              return Center(
                child: Text('Image not found!'), // Handle image loading error
              );
            },
          ),
        ),
        Positioned.fill(
          child: BackdropFilter(
            filter: ImageFilter.blur(
                sigmaX: 2.5, sigmaY: 2.5), // Adjusted blur intensity
            child: Container(
              color: Colors.black
                  .withOpacity(0.3), // Adjust overlay opacity and color
            ),
          ),
        ),
        Align(
          alignment: Alignment.topCenter,
          child: Builder(
            builder: (context) {
              return SingleChildScrollView(
                padding: const EdgeInsets.only(top: 150.0),
                child: Column(
                  children: <Widget>[
                    Container(
                      height: 200,
                      child: PageView(
                        controller: _controller,
                        children: [
                          _buildPageViewContent(),
                        ],
                      ),
                    ),
                    SizedBox(height: 6),
                    Container(
                      width: double.infinity,
                      height: 778,
                      decoration: BoxDecoration(
                        color: Colors.white,
                        borderRadius: BorderRadius.circular(20.0),
                      ),
                      child: Column(
                        children: [
                          SizedBox(height: 15),
                          Container(
                            width: double.infinity,
                            // Full width of the parent container
                            padding: EdgeInsets.symmetric(
                                horizontal: 17.0, vertical: 10.0),
                            // Add horizontal padding
                            child: Align(
                              alignment: Alignment.centerLeft,
                              // Align the title to the left
                              child: Text(
                                'Marketing Board',
                                style: TextStyle(
                                  fontWeight: FontWeight.bold,
                                  fontSize: 24,
                                  color: Colors.green,
                                ),
                              ),
                            ),
                          ),
                          SizedBox(width: 5.0),
                          Center(
                            child: Container(
                              width: 380,
                              // Width of the new container
                              height: 130,
                              // Increased height to accommodate content
                              decoration: BoxDecoration(
                                borderRadius: BorderRadius.circular(
                                    10.0), // Rounded corners
                              ),
                              child: Row(
                                mainAxisAlignment: MainAxisAlignment
                                    .center, // Center the row content
                                children: [
                                  buildIconButton(
                                    assetPath: 'assets/vegetable.png',
                                    label: 'Vegetables',
                                    onTap: () {
                                      print('Vegetables tapped');
                                    },
                                    color: Colors.green,
                                  ),
                                  SizedBox(width: 24),
                                  buildIconButton(
                                    assetPath: 'assets/fruit.png',
                                    label: 'Fruits',
                                    onTap: () {
                                      print('fruits tapped');
                                    },
                                    color: Colors.green,
                                  ), // Space between images
                                  SizedBox(width: 25),
                                  buildIconButton(
                                    assetPath: 'assets/rice.png',
                                    label: 'Grains',
                                    onTap: () {
                                      print('grains tapped');
                                    },
                                    color: Colors.green,
                                  ), // Space between images
                                  SizedBox(width: 25),
                                  buildIconButton(
                                    assetPath: 'assets/flower.png',
                                    label: 'Flowers',
                                    onTap: () {
                                      print('flowers tapped');
                                    },
                                    color: Colors.green,
                                  ), // Space between images
                                ],
                              ),
                            ),
                          ),
                          SizedBox(height: 15),
                          Container(
                            width: double.infinity,
                            // Full width of the parent container
                            padding: EdgeInsets.symmetric(
                                horizontal: 17.0, vertical: 2.0),
                            // Add horizontal padding
                            child: Align(
                              alignment: Alignment.centerLeft,
                              // Align the title to the left
                              child: Text(
                                '      Millers                 Consumers',
                                style: TextStyle(
                                  fontWeight: FontWeight.bold,
                                  fontSize: 24,
                                  color: Colors.green,
                                ),
                              ),
                            ),
                          ),
                          Row(
                            children: [
                              Material(
                                color: Colors.transparent,
                                // Make the Material transparent
                                child: InkWell(
                                  onTap: () {
                                    // Add your action here for the first container
                                    print('First container tapped');
                                  },
                                  borderRadius: BorderRadius.circular(20.0),
                                  // Match the border radius of the container
                                  child: Container(
                                    margin: EdgeInsets.all(16.0),
                                    width: 170,
                                    height: 100,
                                    decoration: BoxDecoration(
                                      color: Colors.green.withOpacity(0.5),
                                      borderRadius: BorderRadius.circular(
                                          20.0), // Rounded corners
                                    ),
                                    child: Center(
                                      child: Row(
                                        mainAxisAlignment:
                                            MainAxisAlignment.center,
                                        children: [
                                          Image.asset(
                                            'assets/factory.png',
                                            // Path to your image in the assets folder
                                            width: 60,
                                            // Adjust the width of the image
                                            height: 60,
                                            color: Colors
                                                .green, // Adjust the height of the image
                                          ),
                                          SizedBox(width: 8.0),
                                        ],
                                      ),
                                    ),
                                  ),
                                ),
                              ),
                              Material(
                                color: Colors.transparent,
                                // Make the Material transparent
                                child: InkWell(
                                  onTap: () {
                                    // Add your action here for the second container
                                    print('Second container tapped');
                                  },
                                  borderRadius: BorderRadius.circular(20.0),
                                  // Match the border radius of the container
                                  child: Container(
                                    margin: EdgeInsets.all(16.0),
                                    width: 170,
                                    height: 100,
                                    decoration: BoxDecoration(
                                      color: Colors.green.withOpacity(0.5),
                                      borderRadius: BorderRadius.circular(
                                          20.0), // Rounded corners
                                    ),
                                    child: Center(
                                      child: Row(
                                        mainAxisAlignment:
                                            MainAxisAlignment.center,
                                        children: [
                                          Image.asset(
                                            'assets/customer.png',
                                            // Path to your image in the assets folder
                                            width: 60,
                                            // Adjust the width of the image
                                            height: 60,
                                            color: Colors
                                                .green, // Adjust the height of the image
                                          ),
                                          SizedBox(width: 8.0),
                                          // Space between the image and the text
                                        ],
                                      ),
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                          SizedBox(height: 5),
                          Container(
                            width: double.infinity,
                            // Full width of the parent container
                            padding: EdgeInsets.symmetric(
                                horizontal: 17.0, vertical: 10.0),
                            // Add horizontal padding
                            child: Align(
                              alignment: Alignment.centerLeft,
                              // Align the title to the left
                              child: Text(
                                'Storage Units',
                                style: TextStyle(
                                  fontWeight: FontWeight.bold,
                                  fontSize: 24,
                                  color: Colors.green,
                                ),
                              ),
                            ),
                          ),
                          Center(
                            child: Container(
                              width: 380,
                              // Width of the container
                              height: 330,
                              // Increased height to accommodate all content
                              decoration: BoxDecoration(
                                borderRadius: BorderRadius.circular(
                                    10.0), // Rounded corners
                                color: Colors.white, // Background color
                              ),
                              child: ClipRRect(
                                borderRadius: BorderRadius.circular(
                                    10.0), // Apply the same border radius
                                child: Padding(
                                  padding: EdgeInsets.all(10.0),
                                  // Add padding around the content
                                  child: Column(
                                    crossAxisAlignment: CrossAxisAlignment
                                        .start, // Align items to the start
                                    children: [
                                      Row(
                                        crossAxisAlignment:
                                            CrossAxisAlignment.start,
                                        // Align items to the top
                                        children: [
                                          SizedBox(
                                            width: 60,
                                            // Desired width of the image
                                            height: 60,
                                            // Desired height of the image
                                            child: Image.asset(
                                              'assets/warehouse.png',
                                              color: Colors
                                                  .green, // Apply a color filter if needed
                                            ),
                                          ),
                                          SizedBox(width: 10.0),
                                          // Space between the image and the text
                                          Expanded(
                                            child: Column(
                                              crossAxisAlignment:
                                                  CrossAxisAlignment.start,
                                              // Align text to the start
                                              children: [
                                                Text(
                                                  'National Agricultural Cooperative Marketing Federation of India (NAFED)',
                                                  // Your desired text
                                                  style: TextStyle(
                                                    fontSize: 16,
                                                    // Adjust text size as needed
                                                    fontWeight: FontWeight.bold,
                                                    // Make the text bold
                                                    color: Colors
                                                        .green, // Adjust text color
                                                  ),
                                                  overflow:
                                                      TextOverflow.ellipsis,
                                                  // Add ellipsis if text overflows
                                                  maxLines:
                                                      2, // Limit text to 2 lines
                                                ),
                                                SizedBox(height: 5.0),
                                                // Space between the text and storage details
                                                Text(
                                                  'City: New Delhi',
                                                  // City name
                                                  style: TextStyle(
                                                    fontSize:
                                                        14, // Adjust text size
                                                    fontWeight: FontWeight.bold,
                                                    color: Colors
                                                        .green, // Adjust text color
                                                  ),
                                                ),
                                                SizedBox(height: 10.0),
                                                // Space between city name and storage details
                                                Text(
                                                  'Storage: 1500 tons',
                                                  // Example storage details
                                                  style: TextStyle(
                                                    fontSize:
                                                        14, // Adjust text size
                                                    color: Colors
                                                        .black54, // Adjust text color
                                                  ),
                                                ),
                                                SizedBox(height: 10.0),
                                                // Space between storage details and price
                                                Text(
                                                  'Rent Price: ₹5000 per month',
                                                  // Example rent price
                                                  style: TextStyle(
                                                    fontSize:
                                                        14, // Adjust text size
                                                    color: Colors
                                                        .black54, // Adjust text color
                                                  ),
                                                ),
                                              ],
                                            ),
                                          ),
                                        ],
                                      ),
                                      SizedBox(height: 10.0),
                                      Divider(),
                                      // Adds a divider line between the content and buttons
                                      Wrap(
                                        spacing: 10.0,
                                        // Space between buttons
                                        runSpacing: 10.0,
                                        // Space between rows of buttons if they wrap
                                        children: [
                                          SizedBox(
                                            width:
                                                110, // Fixed width for buttons
                                            child: ElevatedButton(
                                              onPressed: () {
                                                // Handle storage details action
                                              },
                                              child: Text(
                                                'Details',
                                                style: TextStyle(
                                                  fontSize: 15,
                                                  fontWeight: FontWeight.bold,
                                                ),
                                              ),
                                              style: ElevatedButton.styleFrom(
                                                backgroundColor: Colors
                                                    .green, // Button color
                                              ),
                                            ),
                                          ),
                                          SizedBox(
                                            width:
                                                110, // Fixed width for buttons
                                            child: ElevatedButton(
                                              onPressed: () {
                                                // Handle view location action
                                              },
                                              child: Text(
                                                'Location',
                                                style: TextStyle(
                                                  fontSize: 15,
                                                  fontWeight: FontWeight.bold,
                                                ),
                                              ),
                                              style: ElevatedButton.styleFrom(
                                                backgroundColor: Colors
                                                    .green, // Button color
                                              ),
                                            ),
                                          ),
                                          SizedBox(
                                            width:
                                                110, // Fixed width for buttons
                                            child: ElevatedButton(
                                              onPressed: () {
                                                // Handle the booking action
                                              },
                                              child: Text(
                                                'Book',
                                                style: TextStyle(
                                                  fontSize: 15,
                                                  fontWeight: FontWeight.bold,
                                                ),
                                              ),
                                              style: ElevatedButton.styleFrom(
                                                backgroundColor: Colors
                                                    .green, // Button color
                                              ),
                                            ),
                                          ),
                                        ],
                                      ),
                                    ],
                                  ),
                                ),
                              ),
                            ),
                          ),
                        ], // content viewers for marketing baords
                      ),
                    )
                  ],
                ),
              );
            },
          ),
        )
      ],
    );
  }

  Widget _buildPageViewContent() {
    return SingleChildScrollView(
      scrollDirection: Axis.horizontal, // Enable horizontal scrolling
      child: Row(
        children: <Widget>[
          SizedBox(width: 20), // Add some padding to the left
          _buildVegetableCard(
              "assets/vegetables/onionbig.png", "Wholesale", "1Kg/₹48"),
          SizedBox(width: 10), // Reduce space between cards
          _buildVegetableCard(
              "assets/vegetables/tomato.png", "Wholesale", "1Kg/₹22"),
          SizedBox(width: 10),
          _buildVegetableCard(
              "assets/vegetables/potato.png", "Wholesale", "1Kg/₹39"),
          SizedBox(width: 20),
          _buildVegetableCard(
              "assets/vegetables/brinjal.png", "Wholesale", "1Kg/₹50"),
          SizedBox(width: 10), // Reduce space between cards
          _buildVegetableCard(
              "assets/vegetables/cabbage.png", "Wholesale", "1Kg/₹52"),
          SizedBox(width: 10),
          _buildVegetableCard(
              "assets/vegetables/beetroot.png", "Wholesale", "1Kg/₹43"),
          SizedBox(width: 20),
          _buildVegetableCard(
              "assets/vegetables/butterbeans.png", "Wholesale", "1Kg/₹43"),
          SizedBox(width: 20),
          _buildVegetableCard(
              "assets/vegetables/carrot.png", "Wholesale", "1Kg/₹70"),
          SizedBox(width: 10), // Reduce space between cards
          _buildVegetableCard(
              "assets/vegetables/bottlegourd.png", "Wholesale", "1Kg/₹63"),
          SizedBox(width: 10),
          _buildVegetableCard(
              "assets/vegetables/capsicum.png", "Wholesale", "1Kg/₹45"),
          SizedBox(width: 20), // Add some padding to the right
        ],
      ),
    );
  }

  Widget _buildVegetableCard(String imagePath, String title, String price) {
    return Container(
      height: 150,
      width: 100,
      decoration: BoxDecoration(
        borderRadius: BorderRadius.circular(8.0),
      ),
      child: Column(
        children: [
          SizedBox(height: 5),
          Image.asset(
            imagePath,
            height: 90,
            width: 90,
          ),
          Text(
            title,
            style: TextStyle(
                color: Colors.white, fontWeight: FontWeight.bold, fontSize: 17),
          ),
          Text(
            price,
            style: TextStyle(
                color: Colors.white, fontWeight: FontWeight.bold, fontSize: 15),
          ),
        ],
      ),
    );
  }
}

Widget buildIconButton({
  required String assetPath,
  required String label,
  required VoidCallback onTap,
  required Color color,
}) {
  return Flexible(
    child: Material(
      color: Colors.transparent, // Transparent background
      child: InkWell(
        onTap: onTap,
        splashColor: color.withOpacity(0.3), // Splash color
        borderRadius: BorderRadius.circular(35.0), // Rounded splash effect
        child: Container(
          alignment: Alignment.center,
          child: Column(
            mainAxisAlignment:
                MainAxisAlignment.center, // Center the column content
            children: [
              ColorFiltered(
                colorFilter: ColorFilter.mode(
                  color, // Color to filter
                  BlendMode.srcIn, // Blend mode to apply color
                ),
                child: Image.asset(
                  assetPath, // Path to the image asset
                  width: 65,
                  height: 65,
                  fit: BoxFit.cover,
                ),
              ),
              SizedBox(height: 4), // Space between image and label
              Text(
                label,
                style: TextStyle(
                  color: color,
                  fontWeight: FontWeight.bold,
                  fontSize: 14,
                ),
              ),
            ],
          ),
        ),
      ),
    ),
  );
}

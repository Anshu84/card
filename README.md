//import 'dart:nativewrappers/_internal/vm/lib/mirrors_patch.dart';

import 'package:flutter/material.dart';
import 'package:flutter/services.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
        useMaterial3: true,
      ),
      debugShowCheckedModeBanner: false,
      home: const MyHomePage(),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({
    super.key,
  });

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  final _formkey = GlobalKey<FormState>();
  Size? size;
  final TextEditingController _nameController = TextEditingController();
  final TextEditingController _gmailController = TextEditingController();
  final TextEditingController _phoneController = TextEditingController();
  final TextEditingController _passController = TextEditingController();
  bool isView = false;

  void initState() {
    super.initState();
  }

  @override
  Widget build(BuildContext context) {
    size = MediaQuery.of(context).size;
    return Scaffold(
      body: SingleChildScrollView(
        scrollDirection: Axis.vertical,
        child: Stack(fit: StackFit.loose, children: [
          Image.asset(
            "assets/images/BLACK.png",
            height: size!.height,
            fit: BoxFit.cover,
          ),
          Padding(
            padding: const EdgeInsets.all(15.0),
            child: Card(
              elevation: 3,
              color: Colors.white,
              child: Column(
                mainAxisAlignment: MainAxisAlignment.center,
                crossAxisAlignment: CrossAxisAlignment.center,
                mainAxisSize: MainAxisSize.max,
                children: [
                  SizedBox(height: 20),
                  // SizedBox(height: 300),
                  Center(
                    child: Text(
                      "Sign Up",
                      style: TextStyle(
                        fontSize: 40,
                      ),
                    ),
                  ),

                  Padding(
                    padding: EdgeInsets.all(8),
                    child: Form(
                      key: _formkey,
                      child: Column(
                        crossAxisAlignment: CrossAxisAlignment.center,
                        mainAxisAlignment: MainAxisAlignment.center,
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          SizedBox(height: 20),
                          Row(
                            mainAxisAlignment: MainAxisAlignment.center,
                            crossAxisAlignment: CrossAxisAlignment.center,
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              const Icon(Icons.person,
                                  size: 30, color: Colors.black),
                              SizedBox(
                                width: 10,
                              ),
                              SizedBox(
                                width: size!.width * 0.6,
                                child: TextFormField(
                                    controller: _nameController,
                                    decoration: InputDecoration(
                                      hintText: "Enter full name",
                                      hintStyle: TextStyle(
                                        color: Colors.grey.shade500
                                      ),
                                      border: UnderlineInputBorder(),
                                    ),
                                    keyboardType: TextInputType.name,
                                    validator: (value) {
                                      if (value == null || value.isEmpty) {
                                        return "Please enter some text";
                                      }
                                      return null;
                                    }),
                              ),
                            ],
                          ),
                          Row(
                            mainAxisAlignment: MainAxisAlignment.center,
                            crossAxisAlignment: CrossAxisAlignment.center,
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              const Icon(Icons.g_mobiledata_sharp,
                                  size: 24, color: Colors.black),
                              SizedBox(
                                width: 10,
                              ),
                              SizedBox(
                                width: size!.width * 0.6,
                                child: TextFormField(
                                    controller: _gmailController,
                                    decoration: InputDecoration(
                                      hintText: "Please enter gmail",
                                      border: UnderlineInputBorder(),
                                    ),
                                    keyboardType: TextInputType.emailAddress,
                                    validator: (value) {
                                      if (value == null || value.isEmpty) {
                                        return "Please enter email";
                                      }
                                      return null;
                                    }),
                              ),
                            ],
                          ),
                          Row(
                            mainAxisAlignment: MainAxisAlignment.center,
                            crossAxisAlignment: CrossAxisAlignment.center,
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              const Icon(Icons.password,
                                  size: 24, color: Colors.black),
                              SizedBox(
                                width: 10,
                              ),
                              SizedBox(
                                width: size!.width * 0.6,
                                child: TextFormField(
                                    controller: _passController,
                                    decoration: InputDecoration(
                                      hintText: "Please enter password",
                                      border: UnderlineInputBorder(),
                                    ),
                                    keyboardType: TextInputType.visiblePassword,
                                    validator: (value) {
                                      if (value == null || value.isEmpty) {
                                        return "Please enter some text";
                                      }
                                      return null;
                                    }),
                              ),
                            ],
                          ),
                          Row(
                            mainAxisAlignment: MainAxisAlignment.center,
                            crossAxisAlignment: CrossAxisAlignment.center,
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              const Icon(Icons.phone,
                                  size: 24, color: Colors.black),
                              SizedBox(
                                width: 10,
                              ),
                              SizedBox(
                                width: size!.width * 0.6,
                                child: TextFormField(
                                    controller: _phoneController,
                                    decoration: InputDecoration(
                                        focusColor: Colors.grey.shade300,
                                        fillColor: Colors.grey.shade300,
                                        hintText: "Please enter mobile number",
                                        border: UnderlineInputBorder(borderSide: BorderSide(
                                          color: Colors.grey.shade300, strokeAlign: 0.2, style: BorderStyle.none
                                        )),
                                        enabledBorder: UnderlineInputBorder(borderSide: BorderSide(
                                            color: Colors.grey.shade300, strokeAlign: 0.2, style: BorderStyle.solid))),

                                    keyboardType: TextInputType.phone,
                                    validator: (value) {
                                      if (value == null || value.isEmpty) {
                                        return "Please enter some text";
                                      }
                                      return null;
                                    }),
                              ),
                            ],
                          ),
                          SizedBox(height: 120),
                          SizedBox(
                            width: size!.width / 2,
                            child: ElevatedButton(
                              style: ButtonStyle(
                                backgroundColor:
                                    WidgetStatePropertyAll(Colors.blueAccent),
                              ),
                              onPressed: () {},
                              child: Text("Continue",
                                  style: TextStyle(
                                      fontSize: 24, color: Colors.white54)),
                            ),
                          ),
                          SizedBox(height: 20),





                        ],
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ]),
      ),
    );
  }
}
# card

5. a) Learn about stateful and stateless widgets. 
 
import 'package:flutter/material.dart'; 
 
void main() { 
  runApp(const MyApp()); 
} 
 
class MyApp extends StatelessWidget { 
  const MyApp({super.key}); 
 
  @override 
  Widget build(BuildContext context) { 
    return MaterialApp( 
      title: 'Stateless vs Stateful Demo', 
      debugShowCheckedModeBanner: false, 
      home: const HomePage(), 
    ); 
  } 
} 
 
class HomePage extends StatelessWidget { 
  const HomePage({super.key}); 
 
  @override 
  Widget build(BuildContext context) { 
    return Scaffold( 
      appBar: AppBar( 
        title: const Text('Stateless vs Stateful'), 
        centerTitle: true, 
        backgroundColor: const Color(0xFFD32F2F), 
        foregroundColor: Colors.white, 
      ), 
      backgroundColor: Colors.teal[50], 
      body: Padding( 
        padding: const EdgeInsets.all(20.0), 
        child: Column( 
          mainAxisAlignment: MainAxisAlignment.center, 
          children: [ 
            StaticTextWidget(), 
            const SizedBox(height: 30), 
            CounterWidget(), 
          ], 
        ), 
      ), 
    ); 
  } 
} 
 
class StaticTextWidget extends StatelessWidget { 
  const StaticTextWidget({super.key}); 
 
  @override 
  Widget build(BuildContext context) { 
    return Card( 
      child: Center( 
        child: Padding(padding: EdgeInsets.all(12), 
          child: Column( 
            children: [ 
              Text('Stateless Widget Example', 
                  style: TextStyle( 
                      fontSize: 16, 
                      fontWeight: FontWeight.bold, 
                      color: Color(0xFFE91E63), 
                  ) 
              ), 
              const SizedBox(height: 8), 
              Text('I am a Stateless Widget.\nI never change once built.', 
                textAlign: TextAlign.center, 
                style: TextStyle(fontSize: 16, color: Colors.black87 
                ), 
              ) 
            ], 
          ), 
        ), 
      ), 
    ); 
  } 
} 
 
 
class CounterWidget extends StatefulWidget { 
  const CounterWidget({super.key}); 
 
  @override 
  State<CounterWidget> createState() => _CounterWidgetState(); 
} 
 
class _CounterWidgetState extends State<CounterWidget> { 
  int count = 0; 
 
  void incrementCounter() { 
    setState(() { 
      count++; 
    }); 
  } 
 
  @override 
  Widget build(BuildContext context) { 
    return Card( 
      child: Center( 
        child: Padding(padding: EdgeInsets.all(12), 
          child: Column( 
            children: [ 
              Text('StateFull Widget Example', 
                  style: TextStyle( 
                    fontSize: 16, 
                    fontWeight: FontWeight.bold, 
                    color: Color(0xFF009688), 
                  ) 
              ), 
              const SizedBox(height: 8), 
              Text( 
                'Counter: $count', 
                style: const TextStyle(fontSize: 20, color: Colors.black),
                     ), 
              const SizedBox(height: 10), 
              ElevatedButton.icon( 
                onPressed: incrementCounter, 
                icon: const Icon(Icons.add), 
                label: const Text('Increment'), 
                style: ElevatedButton.styleFrom( 
                  backgroundColor: const Color(0xFFE91E63), 
                  foregroundColor: Colors.white, 
                ), 
              ), 
            ], 
          ), 
        ), 
      ), 
    ); 
  } 
} 


 
 

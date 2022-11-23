https://www.geeksforgeeks.org/singleton-class-in-android/


The Singleton Pattern is a software design pattern that restricts the instantiation of a class to just “one” instance. It is used in Android Applications when an item needs to be created just once and used across the board.
The main reason for this is that repeatedly creating these objects, uses up system resources.

```kotlin
class singleTonExample {
	@Volatile
	private var INSTANCE: singleTonExample? = null

	fun getInstance(): singleTonExample? {
		if (INSTANCE == null) {
			synchronized(this) {
				if (INSTANCE == null) {
					INSTANCE = singleTonExample()
				}
			}
		}
		return INSTANCE
	}
}

```

## synchronized(Lock '\<Any>'){}
  The synchronized(){} method belongs to the category of multithreading concepts. It is used to stop threads from simultaneously accessing in any way the code that this method encapsulates.

It takes one parameter which is by convention named LOCK and of type Any() in kotlin.

The way it works is just like a talking stick does. whichever thread holds the LOCK gets to access the stuff inside the synchronized method, all other threads must wait in line (will be paused) until they receive the LOCK. No worries you do not have to handle the passing of the LOCK itself between the threads, they will just get in line and obtain it once the thread in front of them is done executing the code inside the synchronized method.

https://medium.com/@barryalan2633/what-does-synchronized-and-lock-do-8b8b2ba4a7a9  

## @volatile 
  The @volatile annotation is part of the Kotlin programming language, and it is used for multithreading operations.

We use this annotation to denote that a variable must be read from this specific place in memory every time and therefore not cached anywhere, as some threading operations might do in the background, which if you are not aware of can lead to errors, and we don’t like those here.

  https://medium.com/@barryalan2633/what-does-volatile-do-bae08c8404ff


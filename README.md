# Android--FAQ-s
This is repository containing android interview questions.


Basic Start:
1.Tell me about yourself
2.Which project was more challenging for you, what challenges you faced and how you complete the project? 

1.Rate yourself in java out of 10: 8.5
Java Basic Programming: 
1. Please tell me the feature of OOPS
	Classes & Objects, Inheritance, Polymorphism, Abstraction
2. What is polymorphism & it's type? RunTime and CompileTime
	Ability of objects to morph into multiple of types. Method Overriding and Method Overloading is part of polymorphism.
3.  can we override static method in java? : NO, They are class methods
4. Abstract class vs interface : where to implement these different two?
5. What is singleton in java? 
Single instance through out the application. 
6. How do you create singleton in java?
You need make constructor of the class private. Then create a public static INSTANCE variable of the class to provide access to the client classes.
7. Java 8 Features : Streams, Functions,
8.What are lambdas?
Lambdas are shorter way to writing functions. 
9.What is immutablity in java? More at
10. Why string is immutable?
10.How you can create a immutable class? : Check
11. Final vs finally
12.What is Effectively Final Variables in java?
13. throw vs throws keyword
14. Linked list and Array List
16. What to do to check a instance equality?
	By equals() method. == check 
17. What is composition in OOPS?
18. What are closures?
  
 17. Explain Generics in Java?
18.What is the difference between a Checked Exception and an Un-Checked Exception?


Kotlin Programming: ()
1. Rate yourself in KOTLIN out of 10 : 6
2. How you will achieve static in kotlin.
	By Companion object, all the field and methods declared in companion object of class is static.
3. val vs const val? More at
   	Both are immutable type of, however in you can assign value to val variable on run time
4. lateinit vs lazy keyword : Answer
5. Class vs object keyword More at
An object is a singleton. You do not need to create an instance to use it.  A class needs to be instantiated to be used, In the same way that in Java you may say Math.sqrt(2) and you dont need to create a Math instance to use sqrt, in Kotlin you can create an object to hold these methods, and they are effectively static.
7. There is keyword open what is it? More at
In Kotlin, all the classes are final by default i.e. they can’t be inherited by default. This is opposite to what we learned in Java. In Java, you have to make your class final explicitly.                  	So, to make a class inheritable to the other classes, you must mark it with the open keyword otherwise you will get an error saying “type is final so can’t be inherited”.                                   	Just like classes, all the functions in Kotlin are by default final in nature i.e. you can’t override a function when the function is final in nature.                          	                                            	Just like classes and functions, the variables in Kotlin are by default final in nature. So, to override it in the Child class, you need to set the variables as open in the Base class.
8. What are extension functions?
        	Kotlin gives programmer the ability to add more functionality to the existing classes, without inheriting them. This is achieved through a feature known as extensions. You can add a function is added to existing class it, to add an extension function to a class define a new function appended to class name with . operator.
                    	fun Context.hideKeyboard(){ }


 9. what are scope functions in kotlin?  More at
 	    	Scoped functions are functions that execute a block of code within the context of an object. These functions provide a way to give temporary scope to the object under consideration where specific operations can be applied to the object within the block of code, thereby, resulting in a clean and concise code. There are 5 of them let, apply, also, with, run
10. What is the difference between Java field and Kotlin property? More at
11. What's Null Safety and Nullable Types in Kotlin? what is elvis operator?
12. What higher order functions?
13. Limitation of Data classes?
13. how will you achieve singleton in kotlin?
15. JvmStatic, JvmOverloads, and JvmField in Kotlin? More at
16. What are Inline functions. NoInline and Crossinline
17. What is delegation? How to achieve it in kotlin?
18. takeif and takeUnless?
19. Are there any Ternary operators in kotlin?
20. What is Synchronized keyword do in kotlin?
21. What are the types of equality in Kotlin? == and ===? More at
22. Is Kotlin "pass-by-value" or "pass-by-reference"?

22.what is infix expressions? More at
23. Data class vs normal class? 











Android Basic: 8
Basic:
1. Explain components of android app?
	Activity, Fragments, Broadcast Reciever, Services, Content Providers
2. Explain Activity Lifecycle method? More at
	onCreate(), onStart(), onResume(), onPause(), onStop, onDestroy()
3. What is intent and it's type?
	It’s messaging mechanism for devlivering data from one part of the app to other component. 2 type of Intent
4. Implicit vs explicit intent? More at
5. Intent filter
6. Pending intent
5. If no required component found for intent found then what will happen?
	It will throw ActivityNotFound Exception and app will crash. So it’s always advice to cover you startActivity(intent) with try/catch block or check if component is present 
6. When app will go in background which lifecycle activity method calls?
        	onPause(), onStop() only
        	onDestroy() will only calls whenever you destroy your activity like pressing recent button and remove app from background.
7. what is a fragment? How you can pass value in fragments from activity.?
8. You’re replacing one Fragment with another — how do you ensure that the user can return to the previous Fragment, by pressing the Back button?
supportFragmentManager.beginTransaction().replace(R.id.flcontainer, MyListFragment()).addToBackstack([TAG_HERE]).commit()
9.  onactivityresult is deprecated what is the alternative?  More at
10. what is contentproviders? How would you access data in a ContentProvider?
11. What is a Constraint layout? Barrier vs Guidelines?
12.  What is chaining what does it do?
13. What is your approach to create a multiview recyclerview?
14. What is MVVM design pattern?
15. Compare MVP and MVVM? More at
16. Presenter vs Viewmodel? More at
   	In MVP, the Presenter holds a reference to a View, usually via interfaces. When the Presenter computes new data, it is him who is responsible to call the right method on the View/Interface to update the UI.
In MVVM, the ViewModel "simply exposes" data (usually via LiveData or Rx) so it can be observed. It is not responsible for who is observing the data, and what is done with it. The view then observes that said data in the ViewModel, and updates its UI when the data changes.
 17. Viewmodel vs androidviewmodel
18.Can we write Android UI related code in MVVM's ViewModel?
        	No it’s not advisable to pass any android UI component to viewmodel.
19. what are suspend functions in kotlin? More at
The suspend keyword means that this function can be blocking. Such a function can suspend a buildSequence coroutine. Suspending functions can be created as standard Kotlin functions, but we need to be aware that we can only call them from within a coroutine. Otherwise, we'll get a compiler error
19. What are coroutines? Different dispatchers?? More at
     More
 
20. async vs launch? More at
·          launch is used to fire and forget coroutine. It is like starting a new thread. If the code inside the launch terminates with exception, then it is treated like uncaught exception in a thread -- usually printed to stderr in backend JVM applications and crashes Android applications. join is used to wait for completion of the launched coroutine and it does not propagate its exception. However, a crashed child coroutine cancels its parent with the corresponding exception, too.
·         async is used to start a coroutine that computes some result. The result is represented by an instance of Deferred and you must use await on it. An uncaught exception inside the async code is stored inside the resulting Deferred and is not delivered anywhere else, it will get silently dropped unless processed. You MUST NOT forget about the coroutine you’ve started with async.
 
21. Thread vs Coroutine?  More at
20. SharedPrefrences apply vs commit?
21. what is a service?
22. Service vs  Intent Service? More at
23. bound service vs service?
24. What is context? type of context? : Unable to explain
26. How would you update the UI of an activity from a background service? More at
	Simplest way to achieve this is use local broadcaster and sendBroadcast() fxn and unregister broadcast after usage. 
27. What is DI? Have you implemented DAGGER? Bind vs provide
28. What is data binding? How to achieve inverse data binding? @={}
29. What is a live data? Live data vs MutableLiveData? Set vs Post? 
30. What are Android app bundles? How it is different from traditional app bundling package
32. what is Repository?
33. Parcelable vs Serializable?
34. What is handler android?
35. Payment gateways? UPI integration.
36. Do fragments really need an empty constructor?
37. Transient annotation in kotlin?
38. What is multidex? More at

Git: (Good)
1. Git rebase vs Merge
2. How to merge code on daily basis and how to pull and push?
3. Code Coverage




Resources: 
1. MindOrk
2. Modern Interview
3. Kotlin Gist
4. Flutter questions
 
 
Coroutines:

ABC of Coroutines: https://www.youtube.com/watch?v=bM7PVVL_5GM

Suspend functions: https://www.youtube.com/watch?v=IQf-vtIC-Uc




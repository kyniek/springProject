# springProject

## InteliJ IDEA
- highlighting setup : Edito -> Color Scheme -> General


## Tips&Tricks
better reactive stream debug - place in method with Mono/Flux : Hooks.onOperatorDebug();



Classic approach to WS : one thread per request - default value is 200 , can be increased but minimal consumption for thread is 1MB 


## Spring init bean order
- nie ma gwarancji kolejności inicjalizacji beanów bez użycia specjalnych annotacji
- annotacje kontrolujące inicjalizację beanów : @Primary, @Order and @Qualifier, @DependsOn


## Reactive Streams
Main interfaces : Publisher, Subscriber, Subscription, Processor

Publisher - represents any data provider, like data source, remote web service etc. 
  Main methods :
    subscribe (Subscriber<? super T> s)

Subscriber
  Main methods :
    onComplete()
    onError(java.lang.Throwable t)
    onNext(T t)
    onSubscribe(Subscription s)

Subscription
  Main methods : 
    cancel()
    request(long n) - n - the strictly positive number of elements to requests to the upstream Publisher

Processor extends Publisher<R>, Subscriber<T>

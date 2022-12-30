# springProject



Classic approach to WS : one thread per request - default value is 200 , can be increased but minimal consumption for thread is 1MB 


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

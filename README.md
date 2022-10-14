# Alt:V RXJS
rxjs converted for Alt:V

## How to use
1) Download a [release](https://github.com/konijima-alt-v/altv-rxjs/releases)
2) Unzip into your resource `shared` directory.
3) You can now use rxjs into your client and server scripts.

## Subject Example
```ts
import * as alt from 'alt-client';
import { Subscription, Subject } from '@Shared/modules/rxjs';

class CoreClient {
    // Define an observable event
    public readonly OnConnected: Subject<void> = new Subject();

    constructor() {
        // trigger the event  
        alt.once('connectionComplete', () => this.OnConnected.next());
    }
}

export const Client = new CoreClient();

// Start listening to the event
const sub: Subscription = Client.OnConnected.subscribe(() => {
   // Do something when the event is triggered
})

// Stop listening
sub.unsubscribe()
```

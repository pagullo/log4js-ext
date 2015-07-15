# Logging Basics #

Logging in log4js-ext is as easy as getting a logger using `Sm.log.Logger.getLogger`, and then calling its `debug`, `info`, `warn`, `error` or `fatal` methods depending on what we want to log:

```javascript

logger = Sm.log.Logger.getLogger('Sm.log.example1');
// A simple log
logger.info( "Information message");
```

Of course, you will want to keep related logs grouped, and that's why you want a logger for: later, you will be able to filter log output by logger.

Advanced formatting is available, to make complex logging easier:

```javascript

// Formatted log
logger.warn( "Message, level={0} (text substitutions={1})", "WARN", 2);

// Even more advanced formatting
logger.error( "Message, level={type} (text substitutions={count})",
{type: "ERROR", count: 2});
```

# Logging Objects #

Last, but not least, it is possible to log objects that will be nicely formatted by the built in log viewer.

```javascript

// Log an object, so that we can later take a look at it
obj = { name: 'John',
dog: {name: 'Spottie', hair: 'brown'},
ratings: [2500]};
logger.debug( {msg: 'Logged an object...', loggedObject: obj});
```

You have probably noticed the {0} or {count} parameters used to format log messages in an easy way.
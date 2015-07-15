## New in log4js-ext 2.0... ##
[Log4js-ext 2.0](https://softdevbuilttolast.wordpress.com/2013/03/26/log4js-ext-2-0-is-out/) is out!

This version adds support for [remote logging](http://softdevbuilttolast.wordpress.com/2013/03/20/remote-logging-for-log4js-ext-2-0/) and an enhanced log viewer window that adds search & highlight capabilities.

Besides, the [API documentation](http://www.softwarementors.com/projects/log4js-ext/doc/api/index.html#!/api) is now available online.

## What is log4js-ext? ##

_log4js-ext_ is a Javascript logging system with [features](#Main_features_of_log4js-ext.md) that closely resemble those of the popular [log4j](http://logging.apache.org/log4j/) or [slf4j](http://www.slf4j.org/) libraries, and works in the [ExtJs](http://www.sencha.com/products/extjs/) ecosystem.

If you are familiar with log4j or any of the manylibraries inspired by it, you will be able to put log4js-ext to work immediately.

## Hello world ##
Just to give you a glimpse, here is a little code that shows from simpler to more advanced logging:

```javascript

logger = Sm.log.Logger.getLogger('Sm.log.example1');
// A simple log
logger.info( "Information message");

// Formatted log
logger.warn( "Message, level={0} (text substitutions={1})", "WARN", 2);

// Even more advanced formatting
logger.error( "Message, level={type} (text substitutions={count})",
{type: "ERROR", count: 2});

// Log an object, so that we can later take a look at it
obj = { name: 'John',
dog: {name: 'Spottie', hair: 'brown'},
ratings: [2500]};
logger.debug( {msg: 'Logged an object...', loggedObject: obj});

```

You have probably noticed the **{0}** or **{count}** parameters used to format log messages in an easy way.

Besides, in the _logger.debug_ call, we have a mysterious **loggedObject**, which is the way  to log arbitrary objects so that we can peruse them later.

How will this look like? Well, if you use the window based log4js-ext log viewer you'll get this,

![http://softdevbuilttolast.files.wordpress.com/2012/07/log4js-ext-log-viewer.png](http://softdevbuilttolast.files.wordpress.com/2012/07/log4js-ext-log-viewer.png)

Of course, you can _sort_ and _filter_ logs by priority, category, message contents and even a value in the logged object.

For example, if you set the _Logged Object_ filter to 'John', you will see just the fourth log. A _neat_ way to find your way through tons of log entries!

If you prefer to use your browser console for log output, you will get something like this:

![http://softdevbuilttolast.files.wordpress.com/2012/07/log4js-ext-console-appender.png](http://softdevbuilttolast.files.wordpress.com/2012/07/log4js-ext-console-appender.png)


_log4js-ext_ provides almost all functionality users of logging libraries such as log4j have come to expect, including _hierarchical loggers_, _customizable appenders_ that can allow you to send log information to a remote server, _customizable formatting_, etc.

If you are not familiar with those libraries, you need not worry: log4js-ext is very easy to use and learn by _doing_.

## Main features of log4js-ext ##
I created this logging system for personal use because I needed a logging library, that provided all of the following functionality:

  * It was a must to have a good **GUI based viewer that allowed me to filter logs by different criteria**: category, priority (info, error, debug, warn...), message content, etc.

  * I needed some way to **group related logs** so that I could distinguish what logs were part of a certain complex operation. I decided to support the NDC concept Log4j supports. Of course, the GUI viewer allows NDC filtering

  * I needed to **log arbitrary objects** at some moment, and see them as **nicely highlighted** JSON. And, of course, log4js-ext should allow searching any value in the logged objects.

  * I needed an **easy way to format log messages**, avoiding hand-made concatenations and formating as much as possible.

  * I wanted it to be **extensible**, meaning I should be able to add support for things such as remote logging, to define new ways to format messages, etc.

  * I wanted it to be **easy to use and familiar** to users of popular log libraries for other languages, such as log4j, logback, etc. Log4js-ext closely resembles log4j.

  * And, of course, I needed **robustness**. This means, among other things, lots of automated [JsTestDriver tests](http://www.softwarementors.com/projects/log4js-ext/test-results/).

Log4js-ext fulfills all these goals, and since I'm quite happy with the outcome, I felt it would be nice to contribute it to the community, much as I did with my [DirectJNgine](http://code.google.com/p/directjngine) project.


## Putting log4js-ext to work ##
After [installing](Install.md) the library you will want to take a look at [logging basics](LoggingBasics.md) to get started. There you fill find information about advanced formatting, too.
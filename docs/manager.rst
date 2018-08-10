=================================================
:class:`OpenTracingManager` --- The trace manager
=================================================

.. py:class:: cdumay_opentracing.OpenTracingManager

    This class manages the opentracing context.

    * It allows to recover using the :code:`opentracing` library the initialized tracer.
    * It manage spans stack

    .. py:classmethod:: cdumay_opentracing.OpenTracingManager.register(clazz, driver)

        Register a driver for the given class

        :param Any clazz: Class managed by the driver.
        :param cdumay_opentracing.OpenTracingDriver driver: Driver to register.

    .. py:classmethod:: cdumay_opentracing.OpenTracingManager.get_driver(obj)

        Find registered driver for the given object

        :param Any obj: object to manipulate
        :return: registered driver for this class
        :rtype: cdumay_opentracing.OpenTracingDriver

    .. py:classmethod:: cdumay_opentracing.OpenTracingManager.tags(obj)

        Extract tags from `carrier` object using a registered driver.

        :param Any obj: object to manipulate
        :return: Tags to add on span
        :rtype: dict

    .. py:classmethod:: cdumay_opentracing.OpenTracingManager.get_current_span()

        Get the current span

        :return: The current span
        :rtype: opentracing.span.Span or None


    .. py:classmethod:: cdumay_opentracing.OpenTracingManager.create_span(obj, name, tags)

        Create a new span

        :param Any obj: Any object
        :param str name: Span name
        :param dict tags: Additional tags
        :return: Span
        :rtype: opentracing.span.Span


    .. py:classmethod:: cdumay_opentracing.OpenTracingManager.finish_span(span)

        Terminate the given span

        :param opentracing.span.Span span: Span to finish


    .. py:classmethod:: cdumay_opentracing.OpenTracingManager.log_kv(span, obj, event, **kwargs)

        Adds a log record to the Span.

        :param opentracing.span.Span span: the Span instance to use.
        :param Any obj: the `carrier` object.
        :param str event: Span event name.
        :param dict kwargs: A dict of string keys and values of any type to log
        :return: Returns the Span itself, for call chaining.
        :rtype: opentracing.span.Span

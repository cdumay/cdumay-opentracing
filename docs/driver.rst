===========================================
:class:`OpenTracingDriver` - Classes driver
===========================================

.. py:class:: cdumay_opentracing.OpenTracingDriver

    .. py:attribute:: FORMAT

        :code:`opentracing.Format` used to load and store span context

    .. py:classmethod:: cdumay_opentracing.OpenTracingDriver.extract(data)

         Extract span context from a `carrier` object

        :param Any data: the `carrier` object.
        :return: a SpanContext instance extracted from `carrier` or None if no such span context could be found.

    .. py:classmethod:: cdumay_opentracing.OpenTracingDriver.inject(span, data)

         Injects the span context into a `carrier` object.

        :param opentracing.span.SpanContext span: the SpanContext instance to inject
        :param Any data: the `carrier` object.


    .. py:classmethod:: cdumay_opentracing.OpenTracingDriver.tags(data)

         Extract tags from `carrier` object.

        :param Any data: the `carrier` object.
        :return: Tags to add on span
        :rtype: dict

    .. py:classmethod:: cdumay_opentracing.OpenTracingDriver.log_kv(span, data, event, **kwargs)

         Adds a log record to the Span.

        :param opentracing.span.Span span: the Span instance to use.
        :param Any data: the `carrier` object.
        :param str event: Span event name.
        :param dict kwargs: A dict of string keys and values of any type to log
        :return: Returns the Span itself, for call chaining.
        :rtype: opentracing.span.Span

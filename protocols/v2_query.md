---
layout: page
title: Specification > Query
header: Pages
---
{% include JB/setup %}

## Simple Querying Mechanism in OpenIGTLink Protocol version 2

In OpenIGTLink version 2, special prefixes GET_, STT_, STP_, and RTS_ are used in the message type field in the header for messages to query and control data flow. Those messages with those special prefix should be defined along with primary message types (for example, STT_TDATA, STP_TDATA and RTS_TDATA should be defined with TDATA).

## GET_ prefix: Query a single message

"GET_&lt;datatype&gt;" query message is used to request for a single message with type &lt;datatype&gt;. The receiver of "GET_&lt;datatype&gt;" message must return a message with type &lt;datatype&gt; and the same name as the query message. A "GET_&lt;datatype&gt;" message without device name requests any available data. If data is not available, a returned message must be null body (data size = 0). A format of "GET_&lt;datatype&gt;" may be defined per data type, if necessary.

## STT_ and STP_ prefixes: Control data flow

"STT_&lt;datatype&gt;" and "STP_&lt;datatype&gt;" query message is used to request to start and stop sending a series of messages. The receiver of "STT_&lt;datatype&gt;" message must return "RTS_&lt;datatype&gt;" message with the same name as the query message to notify that the receiver receives the query. Formats of "STT_&lt;datatype&gt;", "STP_&lt;datatype&gt;" and "RTS_&lt;datatype&gt;" may be defined per data type, if necessary.





<h2>Activity Schema and id fields in Bot Framework</h2>


<h2>Introduction</h2>


Our primary goal here is to look at the identifiers in the activity classes and the rules governing them. These identifiers are important With the addition of handoff features and media added features, we are now dealing with a wide range of different activities. These activities need to be handled differently based on their place of origin, their destination and content. These can be achieved by labelling and classifying the activities.

The activity object is a flat list of name/value pairs, some of which are primitive objects, and some of which are complex (nested). Schema here refers to the skeleton structure that represents the logical view of the entire activity class. It defines how the data is organized and how the relations among them are associated. It formulates all the constraints that are to be applied on the data. This will help us to create a dictionary with suitable key-value pairs in order to classify these activities.


<table>
  <tr>
   <td>Channel
   </td>
   <td>Software that sends and receives activities, and transforms them to and from chat or application behaviors. 
   </td>
  </tr>
  <tr>
   <td>Bot
   </td>
   <td>Software that sends and receives activities, and generates automated, semi-automated, or entirely manual responses. Bots have endpoints that are registered with channels.
   </td>
  </tr>
  <tr>
   <td>Sender
   </td>
   <td>Software transmitting an activity.
   </td>
  </tr>
  <tr>
   <td>Receiver
   </td>
   <td>Software accepting an activity.
   </td>
  </tr>
  <tr>
   <td>Endpoint
   </td>
   <td>A programmatically addressable location where a bot or channel can receive activities.
   </td>
  </tr>
  <tr>
   <td>Address
   </td>
   <td>An identifier or address where a user or bot can be contacted.
   </td>
  </tr>
  <tr>
   <td>Field
   </td>
   <td>A named value within an activity or nested object.
   </td>
  </tr>
  <tr>
   <td>Client
   </td>
   <td>Software that sends and receives activities, typically on behalf of human users. Clients do not have endpoints. Also can be referred to as a user.
   </td>
  </tr>
</table>


The entities sender and receiver are variable and interchangeable. For example, a bot can be the sender and the client can be the receiver and vice versa. When a bot or client sends an activity to a channel, it is typically a request for the activity to be recorded. When a channel sends an activity to a bot or client, it is typically a notification that the activity has already been recorded.

<h2>Schema</h2>



<table>
  <tr>
   <td><strong>Channel ID</strong>
   </td>
   <td>Every Bot Framework channel is identified by a unique ID. The value of the channelId field is of type string.
<p>
Example: "channelId": "slack"
<p>
Channel IDs serve as namespaces for other IDs. Runtime calls in the Bot Framework protocol must take place within the context of a channel; the channel gives meaning to the conversation and account IDs used when communicating. By convention all channel IDs are lowercase.
   </td>
  </tr>
  <tr>
   <td><strong>Channel Account ID</strong>
   </td>
   <td>Every bot and user has an account within each channel. The account contains an identifier (id) and other informative bot non-structural data, like an optional name.
   </td>
  </tr>
  <tr>
   <td><strong>Channel Account Name</strong>
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
<ul>

<li>Channel accounts have meaning only within their associated channel.

<li>More than one ID may resolve to the same account.

<li>Ordinal comparison may be used to establish that two IDs are the same.

<li>There is generally no comparison that can be used to identify whether two different IDs resolve to the same account, bot or person.

<li>The stability of associations between IDs, accounts, mailboxes, and people depends on the channel.
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td><strong>Conversation ID</strong>
   </td>
   <td>
<ul>

<li>Messages are sent and received in the context of a conversation, which is identifiable by ID.

<li>Example: "conversation": { "id": "1234" }

<li>A conversation contains an exchange of messages and other activities. Every conversation has zero or more activities, and every activity appears in exactly one conversation. 

<li>Conversations may be perpetual, or may have distinct starts and ends. The process of creating, modifying, or ending a conversation occurs within the channel (i.e., a conversation exists when the channel is aware of it) and the characteristics of these processes are established by the channel. 

<li>A conversation ID may not necessarily uniquely identify a single conversation within a channel even for a single bot.
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td><strong>Service URL</strong>
   </td>
   <td>
<ul>

<li>Activities are frequently sent asynchronously, with separate transport connections for sending and receiving traffic. 

<li>The serviceUrl field is used by channels to denote the URL where replies to the current activity may be sent. 

<li>The value of the serviceUrl field is of type string.

<li>Channels include the serviceUrl field in all activities they send to bots.

<li>Channels use stable values for the serviceUrl field as bots may persist them for long periods, thus the value typically does not change with time
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td><strong>Timestamp</strong>
   </td>
   <td>The timestamp field records the exact UTC time when the activity occurred.
   </td>
  </tr>
  <tr>
   <td><strong>Activity ID</strong>
   </td>
   <td>Activities are sent and received within the Bot Framework protocol, and these are sometimes identifiable. We can identify activities uniquely using activity ids
<p>
Example: "id": "5678"
<p>
Activity IDs are optional and are generated by the channels to give the bot a way to reference the ID in subsequent API calls, if they are available:
<ul>

<li>Replying to a particular activity

<li>Querying for the list of participants at the activity level

<p>
Not all activities are assigned identities (for example, a typing activity may never be assigned an id.) The value of the id field is of type string.
</li>
</ul>
   </td>
  </tr>
</table>


<h2>Channelwise Identifiers</h2>


<h3>Slack</h3>


<h4>Test</h4>



<table>
  <tr>
   <td><strong>Deployment</strong>
<p>
<strong>Attempt</strong>
   </td>
   <td><strong>Activity Object</strong>
   </td>
   <td><strong>Summary</strong>
   </td>
  </tr>
  <tr>
   <td rowspan="3" >1
   </td>
   <td><code>{"Requestor":{"activityId":null,"user":{"id":"U013YPA2UNB:TBLAX038R","name":"mufaddal.k.bhanpurawa","aadObjectId":null,"role":null},"bot":null,"conversation":{"isGroup":false,"conversationType":null,"id":"B02BNGEJ9U1:TBLAX038R:C02CN11DSGN","name":"bottestmufaddal2","aadObjectId":null,"role":null},"channelId":"slack","serviceUrl":"https://slack.botframework.com/"},"ConnectionRequestTime":"2021-08-30T21:21:47.4069228Z"}</code>
   </td>
   <td>User ID : “<code>U013YPA2UNB:TBLAX038R</code>”
<p>
User Name : “<code>mufaddal.k.bhanpurawa</code>”
<p>
Conversation ID : “<code>B02BNGEJ9U1:TBLAX038R:C02CN11DSGN</code>”
<p>
Conversation name (Group Name) : “<code>bottestmufaddal2</code>”
<p>
Channel ID : “slack”
<p>
Service URL : “<code><a href="https://slack.botframework.com/">https://slack.botframework.com/</a></code>”
   </td>
  </tr>
  <tr>
   <td><code>{"Requestor":{"activityId":null,"user":{"id":"U013YPA2UNB:TBLAX038R","name":"mufaddal.k.bhanpurawa","aadObjectId":null,"role":null},"bot":null,"conversation":{"isGroup":false,"conversationType":null,"id":"B02BNGEJ9U1:TBLAX038R:C02D7BKUAN5","name":"bottestmufaddal1","aadObjectId":null,"role":null},"channelId":"slack","serviceUrl":"https://slack.botframework.com/"},"ConnectionRequestTime":"2021-08-30T21:21:36.0553115Z"}</code>
   </td>
   <td>User ID : “<code>U013YPA2UNB:TBLAX038R</code>”
<p>
User Name : “<code>mufaddal.k.bhanpurawa</code>”
<p>
Conversation ID : “<code>B02BNGEJ9U1:TBLAX038R:C02D7BKUAN5</code>”
<p>
Conversation Name(group name) : “<code>bottestmufaddal1</code>”
<p>
Channel ID : “slack”
<p>
Service URL : “<code><a href="https://slack.botframework.com/">https://slack.botframework.com/</a></code>”
   </td>
  </tr>
  <tr>
   <td><code>{"Requestor":{"activityId":null,"user":{"id":"U013YPA2UNB:TBLAX038R","name":"mufaddal.k.bhanpurawa","aadObjectId":null,"role":null},"bot":null,"conversation":{"isGroup":false,"conversationType":null,"id":"B02BNGEJ9U1:TBLAX038R:D02AV65NPV5","name":null,"aadObjectId":null,"role":null},"channelId":"slack","serviceUrl":"https://slack.botframework.com/"},"ConnectionRequestTime":"2021-08-30T21:14:41.3006338Z"}</code>
   </td>
   <td>User ID : “<code>U013YPA2UNB:TBLAX038R</code>”
<p>
User Name : “<code>mufaddal.k.bhanpurawa</code>”
<p>
Conversation ID : “<code>B02BNGEJ9U1:TBLAX038R:D02AV65NPV5</code>”
<p>
Conversation name (Group Name) : null
<p>
Channel ID : “slack”
<p>
Service URL : “<code><a href="https://slack.botframework.com/">https://slack.botframework.com/</a></code>”
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td><code>{"Requestor":{"activityId":null,"user":{"id":"U013YPA2UNB:TBLAX038R","name":"mufaddal.k.bhanpurawa","aadObjectId":null,"role":null},"bot":null,"conversation":{"isGroup":false,"conversationType":null,"id":"B02BNGEJ9U1:TBLAX038R:D02AV65NPV5","name":null,"aadObjectId":null,"role":null},"channelId":"slack","serviceUrl":"https://slack.botframework.com/"},"ConnectionRequestTime":"2021-08-30T21:36:57.3999137Z"}</code>
   </td>
   <td>User ID : “<code>U013YPA2UNB:TBLAX038R</code>”
<p>
User Name : “<code>mufaddal.k.bhanpurawa</code>”
<p>
Conversation ID : “<code>B02BNGEJ9U1:TBLAX038R:D02AV65NPV5</code>”
<p>
Conversation name (Group Name) : null
<p>
Channel ID : “slack”
<p>
Service URL : “<code><a href="https://slack.botframework.com/">https://slack.botframework.com/</a></code>”
   </td>
  </tr>
</table>


<h4>Results</h4>



<table>
  <tr>
   <td><strong>Property</strong>
   </td>
   <td>Description
   </td>
  </tr>
  <tr>
   <td>User ID
   </td>
   <td>
<ul>

<li>Points to User

<li>Remains stable irrespective of bot instance, does not change irrespective of bot or deployment

<li>Can uniquely identify users
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td>User Name
   </td>
   <td>
<ul>

<li>Points to User

<li>Remains stable irrespective of bot instance, does not change irrespective of bot or deployment

<li>Can be used in complementary to user ID
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td>Conversation ID
   </td>
   <td>
<ul>

<li>Points to conversation

<li>Points to the group in which conversation takes place

<li>Changes for same user in different groups

<li>Remains stable irrespective of bot instance, does not change irrespective of bot or deployment
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td>Conversation Name
   </td>
   <td>
<ul>

<li>In this case, this gives the name of the group in which conversation takes place

<li>Changes for same user in different groups

<li>If conversation does not takes place in group, then property value is null

<li>Remains stable irrespective of bot instance, does not change irrespective of bot or deployment
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td>Channel ID
   </td>
   <td>
<ul>

<li>Slack, points to the channel
</li>
</ul>
   </td>
  </tr>
</table>


<h3>Line</h3>


<h4>Test</h4>



<table>
  <tr>
   <td><strong>Deployment</strong>
<p>
<strong>Attempt</strong>
   </td>
   <td><strong>Activity Object</strong>
   </td>
   <td><strong>Summary</strong>
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td><code>{"Requestor":{"activityId":null,"user":{"id":"U4dc6b214db9b73c54a49929367c33df1","name":"bhanpuramufaddal","aadObjectId":null,"role":null},"bot":null,"conversation":{"isGroup":false,"conversationType":null,"id":"U4dc6b214db9b73c54a49929367c33df1|DZ3UsG1pmHG","name":null,"aadObjectId":null,"role":null},"channelId":"line","serviceUrl":"https://line.botframework.com/"},"ConnectionRequestTime":"2021-08-31T05:25:20.9910045Z"}</code>
   </td>
   <td>User ID : “<code>U4dc6b214db9b73c54a49929367c33df1</code>”
<p>
User Name : “<code>bhanpuramufaddal</code>”
<p>
Conversation ID : “<code>U4dc6b214db9b73c54a49929367c33df1|DZ3UsG1pmHG</code>”
<p>
Conversation name  : null
<p>
Channel ID : “line”
<p>
Service URL : “<code><a href="https://slack.botframework.com/">https://line.botframework.com/</a></code>”
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td><code>{"Requestor":{"activityId":null,"user":{"id":"U4dc6b214db9b73c54a49929367c33df1","name":"bhanpuramufaddal","aadObjectId":null,"role":null},"bot":null,"conversation":{"isGroup":false,"conversationType":null,"id":"U4dc6b214db9b73c54a49929367c33df1|DZ3UsG1pmHG","name":null,"aadObjectId":null,"role":null},"channelId":"line","serviceUrl":"https://line.botframework.com/"},"ConnectionRequestTime":"2021-08-31T05:28:14.9584355Z"}</code>
   </td>
   <td>User ID : “<code>U4dc6b214db9b73c54a49929367c33df1</code>”
<p>
User Name : “<code>bhanpuramufaddal</code>”
<p>
Conversation ID : “<code>U4dc6b214db9b73c54a49929367c33df1|DZ3UsG1pmHG</code>”
<p>
Conversation name  : null
<p>
Channel ID : “line”
<p>
Service URL : “<code><a href="https://slack.botframework.com/">https://line.botframework.com/</a></code>”
   </td>
  </tr>
</table>


<h4>Results</h4>



<table>
  <tr>
   <td><strong>Property</strong>
   </td>
   <td>Description
   </td>
  </tr>
  <tr>
   <td>User ID
   </td>
   <td>
<ul>

<li>Points to User

<li>Remains stable irrespective of bot instance, does not change irrespective of bot or deployment

<li>Can uniquely identify users
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td>User Name
   </td>
   <td>
<ul>

<li>Points to User

<li>Remains stable irrespective of bot instance, does not change irrespective of bot or deployment

<li>Can be used in complementary to user ID
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td>Conversation ID
   </td>
   <td>
<ul>

<li>Points to conversation

<li>Remains stable irrespective of bot instance, does not change irrespective of bot or deployment

<li>Not sure about about the group behaviour of conversation ID
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td>Channel ID
   </td>
   <td>
<ul>

<li>line, points to the channel
</li>
</ul>
   </td>
  </tr>
</table>

![User and Conversation IDs]("/Images/Screen Shot 2021-09-02 at 3.09.07 AM.png?raw=true")

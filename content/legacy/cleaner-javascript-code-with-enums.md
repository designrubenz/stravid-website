---
id: 6
outputs:
  - /en/cleaner-javascript-code-with-enums/index.html
  - /articles/cleaner-javascript-code-with-enums/index.html
  - /6/index.html
language: en
title: Cleaner JavaScript code with Enums
description: Improve your JavaScript code by using enums.
---
<h1>Cleaner JavaScript code with Enums</h1>

<p>
There is a very simple and obvious solution for a enum variable type in Javascript, a object.
Let’s assume we have three values which represent the state of a client in our fictional chat example.
</p>
<ul>
  <li><strong>Value 0</strong>: Normal user</li>
  <li><strong>Value 1</strong>: Moderator, can kick other users</li>
  <li><strong>Value 2</strong>: Administrator, owns the chat</li>
</ul>
<p>
Not every user can kick others out of the chat, so if a user sends the kick command we have to verify if he is allowed to do so.
</p>
<p>
<pre>
if (user.state &gt; 0) {
    // user is allowed to send kick commands
    // process command
}
</pre>
</p>
<p>
Not a very good solution because we place <code>0</code>s, <code>1</code>s and <code>2</code>s in our code which make the code unreadable. So let’s change this, we create a object which contains the different user states and can use this in our code.
With this approach we write readable code and if the value of a state changes there is only one place in the code base where we have to change it.
</p>
<p>
<pre>
var states = {
    USER: 0,
    MOD: 1,
    ADMIN: 2
};

if (user.state &gt; states.USER) {
    // user is allowed to send kick commands
    // process command
}
</pre>
</p>

<div class="call-to-action">
  Do you need help with a messy JavaScript codebase?<br>
  You can <a href="/javascript-consulting-and-development/">hire me for JavaScript consulting and development</a>.<br><br>
  Contact me at <a href="mailto:david.strauss@edgycircle.com">david.strauss@edgycircle.com</a> or +43 664 216 403 4.
</div>

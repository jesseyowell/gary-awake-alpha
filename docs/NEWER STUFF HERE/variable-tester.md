---
title: Variable tester
deprecated: false
hidden: false
metadata:
  robots: index
---
## Variable

hello {user.name}

<br />

\{ function getGreeting(user.name) \{ &#x20;
&#x20; if (user) \{
&#x20;   return \<h1>Hello, \{formatName(user)}!\</h1>;  }
&#x20; return \<h1>Hello, Stranger.\</h1>;} }
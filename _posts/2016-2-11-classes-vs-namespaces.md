---
layout: post
title: Classes VS Namespaces
---

Often classes are used as namespaces for functions:

```php
<?php

class UserController
{
  public function viewAction()
  {
    // Show user
  }
  
  public function removeAction()
  {
    // Remove user
  }
}
```

Methods in the class are not connected. They represent alternative scenarios, and will not be called together in one scenario.

If there is need to group such functions, namespaces should be used:

```php
<?php
namespace User;

function view()
{
  // View user
}

function remove()
{
  // Remove user
}
```

If you need to represent operations, but, for some reason, only objects are allowed, classes with one method (commands) can be used:

```php
<?php 
namespace User;

class View
{
  public function __invoke() // or execute()
  {
  }
}

class Remove
{
  public function __invoke()
  {
  }
}

```

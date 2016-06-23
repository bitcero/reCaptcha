reCaptcha for Common Utilities
====

This is an implementation of **[Google reCaptcha service](https://www.google.com/recaptcha/)** for **[Common Utilities](http://rmcommon.com)** and Xoops. This plugin allows to use reCaptcha in forms from comments or other.

---

### Requirements

* [Xoops 2.5.7+](http://www.xoops.org)
* [Common Utilities 2.3+](http://www.rmcommon.com)
* PHP 5.6+

### Install

**Notice:** The plugin is currently on alpha stage. This plugin must not be used on production environments.

This plugin must be installed as any other plugin for Common Utilities:

1. Download **[latest version](https://github.com/bitcero/reCaptcha/archive/master.zip)** of plugin.
2. Upload directory `recaptcha` contained in ZIP file to directory "`/modules/rmcommon/plugins`" of your XOOPS installation.
3. Go to Common Utilities control panel.
4. Go to Common Utilities **plugins** manager.
5. Click on tab *Available Plugins*.
6. Click on option **Install** below the **reCaptcha for Xoops** name.
7. Done!

After install, if you have any other CAPTCHA service installed, you will need to activate the *reCaptcha* service.

#### Enable reCaptcha Service

1. Go to Common Utilities control panel.
2. Go to `Services Manager`.
3. Locate box for CAPTCHA service and select `reCaptcha for Xoops`.
4. Done! reCaptcha service is now enabled.

---

### How to use the service in your own forms

Use the service for reCaptcha in your own developments is very easy. You need to use the Common Utilities `Service Controller`. Check the next example of integration:

#### Show the widget

```php
if ($common->services()->service('captcha')) {
    $common->services()->service('captcha')->render();    
}
```

Remember to check if `captcha` service is available, otherwise an exception will occurs.

#### Verify the challenge

```php
if ($common->services()->service('captcha')) {
    if($common->services()->service('captcha')->verify()) {
        // Success
    } else {
        // Fail!
    }    
}
```

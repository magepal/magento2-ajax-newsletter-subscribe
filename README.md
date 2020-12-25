<a href="https://www.magepal.com" title="Magento Extensions" ><img src="https://image.ibb.co/dHBkYH/Magepal_logo.png" width="100" align="right" title="Magento Custom Modules" /></a>

# Ajax Newsletter Subscription for Magento 2


### Installation

#### Step 1

##### Using Composer (recommended)

```
composer require magepal/magento2-ajax-newsletter-subscribe
```

##### Manually
* Download the extension
* Unzip the file
* Create a folder {Magento 2 root}/app/code/MagePal/AjaxNewsletterSubscribe
* Copy the content from *unzip folder


#### Step 2 - Enable extension ("cd" to {Magento root} folder)
```
  php -f bin/magento module:enable --clear-static-content MagePal_AjaxNewsletterSubscribe
  php -f bin/magento setup:upgrade
```


### Usage
```javascript
$('#newsletter-validate-detail').submit(function (e) {
    if ($(this).valid()) {
         var url = $form.attr('action');
         var postData = $form.serializeArray();
    
        try {
            $.ajax({
                url: url,
                dataType: 'json',
                type: 'POST',
                showLoader: true,
                data: $.param(postData),
                complete: function (data) {
                    if (typeof data === 'object') {
                        data = data.responseJSON;
                        //json object
                    } else {
                        //Unknown Error
                    }
                }
            });
        } catch (e) {
                //check for errors
        }
    }
    
    return false;
});
```

### Return JSON
```php

$response = [
    'status' => 1,
    'msg' => __('The confirmation request has been sent.'),
];

$response = [
    'status' => 0,
    'msg' => __('There was a problem with the subscription: %1', $e->getMessage()),
];

```

---
- [Custom SMTP](https://www.magepal.com/magento2/extensions/custom-smtp.html)
- [Catalog Hover Image for Magento](https://www.magepal.com/magento2/extensions/catalog-hover-image-for-magento.html)
- [Enhanced Success Page for Magento 2](https://www.magepal.com/magento2/extensions/enhanced-success-page.html)
- [Enhanced Transactional Emails for Magento 2](https://www.magepal.com/magento2/extensions/enhanced-transactional-emails.html)
- [Google Tag Manager](https://www.magepal.com/magento2/extensions/google-tag-manager.html) 
- [Enhanced E-commerce](https://www.magepal.com/magento2/extensions/enhanced-ecommerce-for-google-tag-manager.html) 
- [Reindex](https://www.magepal.com/magento2/extensions/reindex.html) 
- [Custom Shipping Method](https://www.magepal.com/magento2/extensions/custom-shipping-rates-for-magento-2.html) 
- [Preview Order Confirmation](https://www.magepal.com/magento2/extensions/preview-order-confirmation-page-for-magento-2.html)
- [Guest to Customer](https://www.magepal.com/magento2/extensions/guest-to-customer.html) 
- [Admin Form Fields Manager](https://www.magepal.com/magento2/extensions/admin-form-fields-manager-for-magento-2.html) 
- [Customer Dashboard Links Manager](https://www.magepal.com/magento2/extensions/customer-dashboard-links-manager-for-magento-2.html) 
- [Lazy Loader](https://www.magepal.com/magento2/extensions/lazy-load.html) 
- [Order Confirmation Page Miscellaneous Scripts](https://www.magepal.com/magento2/extensions/order-confirmation-miscellaneous-scripts-for-magento-2.html)
- [HTML Minifier for Magento2](https://www.magepal.com/magento2/extensions/html-minifier.html)

© MagePal LLC. | [www.magepal.com](https://www.magepal.com)

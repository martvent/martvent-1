THE CONSTITUTION OF MARTVENT 
IS DIVIDED INTO 
5 SCHEDULES 
250 ARTICLES AND 
550 CLAUSE
AND SEVERAL FOCUS BY WHICH THE CONSTITUTION OF MARTVENT CAN BE EASILY DEFINE.
Preamble, 
we are the happy healthy and wealthy human. we have the responsibility as a human beings to give an opportunity of happiness, health and wealth to all people. This is because, all these three factors are the soul of Humanism. We Can't share happyness without happyness. we can't help anyone without health, we can't give food without work. so it's our duty as to be a responsible human. and if we are a responsible human then we can easily understand how to go without allegation, and to dig the deep ocean, and to take out the Diamond. as for you, who capture my feeling they can be makes me living. On ground of martvent no space of discrimination, no space of Criticism, no space of ganging, not to harm anyone, (physical,mental,social). the piller of constitution is based on compleate sence of humanism. Truth, Non Violence, or anythings which act, or result of act before and after blood and killing, is complete prohibitaed under this constitution area. this constitution is not after and equal to any specific country constitution. but the company constitusion always requst any country to give permision to makes healthy enviroment. as on demand of this licance copy of company constitution. 
## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/martent-marketplace/developer.martvent.com/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/martent-marketplace/developer.martvent.com/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

{code}
View.Phtml
/**
 * Product view template
 *
 * @see Mage_Catalog_Block_Product_View
 * @see Mage_Review_Block_Product_View
 */
?>
<?php $_helper = $this->helper('catalog/output'); ?>
<?php $_product = $this->getProduct(); ?>
<script type="text/javascript">
    var optionsPrice = new Product.OptionsPrice(<?php echo $this->getJsonConfig() ?>);
</script>
<div id="messages_product_view"><?php echo $this->getMessagesBlock()->toHtml() ?></div>
<div class="product-view">
    <div class="product-essential">
    <form action="<?php echo $this->getSubmitUrl($_product, array('_secure' => $this->_isSecure())) ?>" method="post" id="product_addtocart_form"<?php if($_product->getOptions()): ?> enctype="multipart/form-data"<?php endif; ?>>
        <?php echo $this->getBlockHtml('formkey') ?>
        <div class="no-display">
            <input type="hidden" name="product" value="<?php echo $_product->getId() ?>" />
            <input type="hidden" name="related_product" id="related-products-field" value="" />
        </div>

        <div class="product-shop">
            <div class="product-name">
                <h1><?php echo $_helper->productAttribute($_product, $_product->getName(), 'name') ?></h1>
            </div>

            <?php if ($this->canEmailToFriend()): ?>
                <p class="email-friend"><a href="<?php echo $this->helper('catalog/product')->getEmailToFriendUrl($_product) ?>"><?php echo $this->__('Email to a Friend') ?></a></p>
            <?php endif; ?>

            <?php echo $this->getReviewsSummaryHtml($_product, false, true)?>
            <?php echo $this->getChildHtml('alert_urls') ?>
            <?php echo $this->getChildHtml('product_type_data') ?>
            <?php echo $this->getTierPriceHtml() ?>
            <?php echo $this->getChildHtml('extrahint') ?>

            <?php if (!$this->hasOptions()):?>
                <div class="add-to-box">
                    <?php if($_product->isSaleable()): ?>
                        <?php echo $this->getChildHtml('addtocart') ?>
                        <?php if( $this->helper('wishlist')->isAllow() || $_compareUrl=$this->helper('catalog/product_compare')->getAddUrl($_product)): ?>
                            <span class="or"><?php echo $this->__('OR') ?></span>
                        <?php endif; ?>
                    <?php endif; ?>
                    <?php echo $this->getChildHtml('addto') ?>
                </div>
                <?php echo $this->getChildHtml('extra_buttons') ?>
            <?php elseif (!$_product->isSaleable()): ?>
                <div class="add-to-box">
                    <?php echo $this->getChildHtml('addto') ?>
                </div>
            <?php endif; ?>

            <?php if ($_product->getShortDescription()):?>
                <div class="short-description">
                    <h2><?php echo $this->__('Quick Overview') ?></h2>
                    <div class="std"><?php echo $_helper->productAttribute($_product, nl2br($_product->getShortDescription()), 'short_description') ?></div>
                </div>
            <?php endif;?>

            <?php echo $this->getChildHtml('other');?>

            <?php if ($_product->isSaleable() && $this->hasOptions()):?>
                <?php echo $this->getChildChildHtml('container1', '', true, true) ?>
            <?php endif;?>

        </div>

        <div class="product-img-box">
            <?php echo $this->getChildHtml('media') ?>
        </div>

        <div class="clearer"></div>
        <?php if ($_product->isSaleable() && $this->hasOptions()):?>
            <?php echo $this->getChildChildHtml('container2', '', true, true) ?>
        <?php endif;?>
    </form>
    <script type="text/javascript">
    //<![CDATA[
        var productAddToCartForm = new VarienForm('product_addtocart_form');
        productAddToCartForm.submit = function(button, url) {
            if (this.validator.validate()) {
                var form = this.form;
                var oldUrl = form.action;
                if (url) {
                   form.action = url;
                }
                var e = null;
                try {
                    this.form.submit();
                } catch (e) {
                }
                this.form.action = oldUrl;
                if (e) {
                    throw e;
                }
                if (button && button != 'undefined') {
                    button.disabled = true;
                }
            }
        }.bind(productAddToCartForm);
        productAddToCartForm.submitLight = function(button, url){
            if(this.validator) {
                var nv = Validation.methods;
                delete Validation.methods['required-entry'];
                delete Validation.methods['validate-one-required'];
                delete Validation.methods['validate-one-required-by-name'];
                // Remove custom datetime validators
                for (var methodName in Validation.methods) {
                    if (methodName.match(/^validate-datetime-.*/i)) {
                        delete Validation.methods[methodName];
                    }
                }
                if (this.validator.validate()) {
                    if (url) {
                        this.form.action = url;
                    }
                    this.form.submit();
                }
                Object.extend(Validation.methods, nv);
            }
        }.bind(productAddToCartForm);
    //]]>
    </script>
    </div>

    <div class="product-collateral">
<?php foreach ($this->getChildGroup('detailed_info', 'getChildHtml') as $alias => $html):?>
        <div class="box-collateral <?php echo "box-{$alias}"?>">
            <?php if ($title = $this->getChildData($alias, 'title')):?>
            <h2><?php echo $this->escapeHtml($title); ?></h2>
            <?php endif;?>
            <?php echo $html; ?>
        </div>
<?php endforeach;?>
        <?php echo $this->getChildHtml('upsell_products') ?>
        <?php echo $this->getChildHtml('product_additional_data') ?>
    </div>
</div>

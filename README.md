This is a [Sublime Text][sublime] package which includes handy snippets for doing Symfony2 framework development.

## Installation ##

### With Package Control ###

If you have the [Package Control][package_control] package installed, you can install Symfony2 Snippets from inside Sublime Text itself. Open the Command Palette and select "Package Control: Install Package", then search for Symfony2 Snippets.

### Without Package Control ###

If you haven't got Package Control installed you will need to make a clone of this repository into your packages folder, like so:

    git clone https://github.com/raulfraile/sublime-symfony2 symfony2-snippets

## Shortcuts ##

### Controller ###

`sfem`

``` php
$em = $this->getDoctrine()->getEntityManager();
```

`sfforward`

``` php
$this->forward('TestBundle:Folder:view', array());
```

`sfredirect`

``` php
$this->redirect($this->generateUrl('route'));
```

`sfrender`

``` php
$this->render('TestBundle:Folder:view.html.twig', array());
```

`sfsession`

``` php
$this->getRequest()->getSession();
```

`sfsetflash`

``` php
this->get('session')->setFlash('notice', 'message');
```

### Doctrine ###

#### Annotations ####

`sfentity`

``` php
**
 * @ORM\Entity
 * @ORM\Table(name="name")
 */
```

`sfidcolumn`

``` php
/**
 * @ORM\Column(name="id", type="integer", nullable=false)
 * @ORM\Id
 * @ORM\GeneratedValue(strategy="IDENTITY")
 */
```

`sfstringcolumn`

``` php
/**
 * @ORM\Column(type="string", length=100)
 */
```

`sfdecimalcolumn`

``` php
/**
 * @ORM\Column(type="decimal", scale=${1:2})
 */
```

`sfstextcolumn`

``` php
/**
 * @ORM\Column(type="text")
 */
```

### YAML ###

 `sfroute`

``` yaml
route_name:
    pattern:   /url
    defaults:  { _controller: AcmeTestBundle:Test:action }
```

[sublime]: http://www.sublimetext.com/
[package_control]: http://wbond.net/sublime_packages/package_control
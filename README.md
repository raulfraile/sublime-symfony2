This is a [Sublime Text][sublime] package which includes handy snippets for doing [Symfony2][symfony2] framework development.

## Installation ##

### With Package Control ###

If you have the [Package Control][package_control] package installed, you can install Symfony2 Snippets from inside Sublime Text itself. Open the Command Palette and select "Package Control: Install Package", then search for Symfony2 Snippets.

### Without Package Control ###

If you haven't got Package Control installed you will need to make a clone of this repository into your packages folder, like so:

    git clone https://github.com/raulfraile/sublime-symfony2 symfony2-snippets

## Shortcuts ##

All shortcuts start with the `sf` prefix and are both short and intuitive:

### Controller ###

`sfcontroller`

``` php
namespace VendorName\Bundle\BundleNameBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;

class ControllerNameController extends Controller
{
    public function indexAction()
    {
        return $this->render('VendorNameBundleNameBundle:ControllerName:index.html.twig');
    }
}
```

`sfem`

``` php
$em = $this->getDoctrine()->getEntityManager();
```

`sfrepo`

``` php
$em->getRepository('Bundle:Repository');
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

### Forms ###

`sfform`

``` php
namespace VendorName\Bundle\BundleNameBundle\Form\Type;

use Symfony\Component\Form\AbstractType;
use Symfony\Component\Form\FormBuilder;

class FormNameType extends AbstractType
{
    public function buildForm(FormBuilder $builder, array $options)
    {
        
    }

    public function getDefaultOptions(array $options)
    {
        return array(
            'data_class' => 'VendorName\\Bundle\\BundleNameBundle\\Entity\\FormName',
        );
    }

    public function getName()
    {
        return 'formName';
    }
}
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

## Contribute ##

If you miss something, feel free to fork this repository and send a PR with your awesome snippets for Symfony2 :)

### Contributors list ###

* Raúl Fraile: [github](http://github.com/raulfraile) | [twitter](http://twitter.com/raulfraile)
* Pierre-Yves LEBECQ: [github](http://github.com/pylebecq) | [twitter](http://twitter.com/pylebecq)

[sublime]: http://www.sublimetext.com/
[symfony2]: http://www.symfony.com
[package_control]: http://wbond.net/sublime_packages/package_control
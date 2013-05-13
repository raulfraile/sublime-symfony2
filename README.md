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

`sfcontrollera`

``` php
namespace VendorName\Bundle\BundleNameBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;
use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;
use Sensio\Bundle\FrameworkExtraBundle\Configuration\Template;

class ControllerNameController extends Controller
{
    /**
     * @Route(route configuration)
     * @Template
     */
    public function indexAction()
    {

    }
}
```

`sfaction`

``` php
public function indexAction()
{
    return $this->render('BundleNameBundle:ControllerName:index.html.twig');
}
```

`sfactiona`

``` php
/**
 * @Route(route configuration)
 * @Template()
 */
public function indexAction()
{

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
$this->get('session')->getFlashBag()->add('notice', 'message');
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

`sfdatatransformer`

``` php
namespace VendorName\Bundle\BundleNameBundle\Form\DataTransformer;

use Symfony\Component\Form\DataTransformerInterface;
use Symfony\Component\Form\Exception\UnexpectedTypeException;
use Symfony\Component\Form\Exception\TransformationFailedException;

class TransformerNameTransformer implements DataTransformerInterface
{
    /**
     * Transforms a value from the original representation to a transformed representation.
     *
     * @param  mixed $value              The value in the original representation
     *
     * @return mixed                     The value in the transformed representation
     *
     * @throws UnexpectedTypeException   when the argument is not a string
     * @throws TransformationFailedException  when the transformation fails
     */
    public function transform($value)
    {

    }

    /**
     * Transforms a value from the transformed representation to its original
     * representation.
     *
     * @param  mixed $value              The value in the transformed representation
     *
     * @return mixed                     The value in the original representation
     *
     * @throws UnexpectedTypeException   when the argument is not of the expected type
     * @throws TransformationFailedException  when the transformation fails
     */
    public function reverseTransform($value)
    {

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

`sfentityClass`

``` php
namespace VendorName\BundleNameBundle\Entity;

use Doctrine\ORM\Mapping as ORM;
use Symfony\Component\Validator\Constraints as Assert;

/*
* @ORM\Entity(repositoryClass="VendorName\BundleNameBundle\Repository\repositoryClassRepository")
* @ORM\Table(name="table_name")
*/
class repositoryClass
{
    /**
    * @ORM\Id
    * @ORM\Column(type="integer")
    * @ORM\GeneratedValue(strategy="AUTO")
    */
    protected $id;
}
```

`sfdocumentClass`

``` php
namespace VendorName\BundleNameBundle\Document;

use Doctrine\ODM\MongoDB\Mapping\Annotations as MongoDB;
use Symfony\Component\Validator\Constraints as Assert;

/**
* @MongoDB\Document(collection="repositoryClass", repositoryClass="VendorName\BundleNameBundle\Repository\repositoryClassRepository")
*/
class repositoryClass
{
    /**
    * @MongoDB\Id
    */
    protected $id;
}
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

`sftextcolumn`

``` php
/**
 * @ORM\Column(type="text")
 */
```

`sfintegercolumn`

``` php
/**
 * @ORM\Column(type="integer")
 */
```

`sfbooleancolumn`

``` php
/**
 * @ORM\Column(type="boolean")
 */
```

`sfsmallintcolumn`

``` php
/**
 * @ORM\Column(type="smallint")
 */
```

`sfbigintcolumn`

``` php
/**
 * @ORM\Column(type="bigint")
 */
```

`sfdatetimecolumn`

``` php
/**
 * @ORM\Column(type="datetime")
 */
```

`sfdatecolumn`

``` php
/**
 * @ORM\Column(type="date")
 */
```

`sftimecolumn`

``` php
/**
 * @ORM\Column(type="time")
 */
```

`sffloatcolumn`

``` php
/**
 * @ORM\Column(type="float")
 */
```

`sfarraycolumn`

``` php
/**
 * @ORM\Column(type="array")
 */
```

`sfobjectcolumn`

``` php
/**
 * @ORM\Column(type="object")
 */
```

### Twig ###

`sftwigextension`

``` php
namespace VendorName\Bundle\BundleNameBundle\Twig\Extension;

class ExtensionNameExtension extends \Twig_Extension
{
    /**
     * Returns a list of filters to add to the existing list.
     *
     * @return array An array of filters
     */
    public function getFilters()
    {
        return array();
    }

    /**
     * Returns a list of tests to add to the existing list.
     *
     * @return array An array of tests
     */
    public function getTests()
    {
        return array();
    }

    /**
     * Returns a list of functions to add to the existing list.
     *
     * @return array An array of functions
     */
    public function getFunctions()
    {
        return array();
    }
}
```

`sftwigform`

``` html
<form class="${1}" action="{{ ${2:path('${3}')} }}" method="${4:post}" {{ form_enctype(form) }}>
    {{ form_widget(form) }}
    <input type="submit" value="${5:Submit}" /> 
</form>
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
* Willemsen Christophe: [github](http://github.com/kwattro) | [twitter](http://twitter.com/kwattroweb)
* Alexandre Salomé: [github](http://github.com/alexandresalome)

[sublime]: http://www.sublimetext.com/
[symfony2]: http://www.symfony.com
[package_control]: http://wbond.net/sublime_packages/package_control

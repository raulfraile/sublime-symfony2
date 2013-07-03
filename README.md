This is a [Sublime Text][sublime] package which includes handy snippets for doing [Symfony2][symfony2] framework development.

**Important:** The `master` branch of this plugin will always be in sync with the latest stable release of Symfony2.
New branches will be created whenever a non backward-compatible change in Symfony2 is introduced into the snippets. So, if you need to work with an older version of Symfony2, please check the branch list to find the branch compatible with the version you are looking for and proceed to a manual install of this branch.

## Installation ##

### With Package Control ###

If you have the [Package Control][package_control] package installed, you can install Symfony2 Snippets from inside Sublime Text itself. Open the Command Palette and select "Package Control: Install Package", then search for Symfony2 Snippets.

### Without Package Control ###

If you haven't got Package Control installed you will need to make a clone of this repository into your packages folder, like so:

    git clone https://github.com/raulfraile/sublime-symfony2 symfony2-snippets

If you need to install a specific branch of the plugin (2.0 in this example), please use the following commands:

    cd symfony2-snippets
    git checkout origin/2.0

## Shortcuts ##

All shortcuts start with the `sf` prefix and are both short and intuitive:

### Controller ###

`sfcontroller`

``` php
use Symfony\Bundle\FrameworkBundle\Controller\Controller;

class DefaultController extends Controller
{
    public function indexAction()
    {
        return $this->render('.html.twig');
    }
}
```

`sfcontrollera`

``` php
use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;
use Sensio\Bundle\FrameworkExtraBundle\Configuration\Template;
use Symfony\Bundle\FrameworkBundle\Controller\Controller;

class DefaultController extends Controller
{
    /**
     * @Route("/", name="")
     * @Template()
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
    return $this->render('.html.twig');
}
```

`sfactiona`

``` php
/**
 * @Route("/", name="")
 * @Template()
 */
public function indexAction()
{

}
```

`sfem`

``` php
$em = $this->getDoctrine()->getManager();
```

`sfrepo`

``` php
$em->getRepository('Bundle:Repository');
```

`sfforward`

``` php
$this->forward('Bundle:Controller:action', array(), array());
```

`sfredirect`

``` php
$this->redirect($this->generateUrl('route', array()));
```

`sfrender`

``` php
$this->render('Bundle:Folder:template.html.twig', array());
```

`sfgetsession`

``` php
$this->getRequest()->getSession();
```

`sfsetflash`

``` php
$this->get('session')->getFlashBag()->add('type', 'message');
```

### Command ###

`sfcommand`

``` php
use Symfony\Component\Console\Command\Command;
use Symfony\Component\Console\Input\InputInterface;
use Symfony\Component\Console\Output\OutputInterface;

class DefaultCommand extends Command
{
    /**
     * {@inheritdoc}
     */
    protected function configure()
    {
        $this
            ->setName('default:command')
            ->setDescription('Default description')
        ;
    }

    /**
     * {@inheritdoc}
     */
    protected function execute(InputInterface $input, OutputInterface $output)
    {

    }
}
```

`sfcommandca`

``` php
use Symfony\Bundle\FrameworkBundle\Command\ContainerAwareCommand;
use Symfony\Component\Console\Input\InputInterface;
use Symfony\Component\Console\Output\OutputInterface;

class DefaultCommand extends ContainerAwareCommand
{
    /**
     * {@inheritdoc}
     */
    protected function configure()
    {
        $this
            ->setName('default:command')
            ->setDescription('Default description')
        ;
    }

    /**
     * {@inheritdoc}
     */
    protected function execute(InputInterface $input, OutputInterface $output)
    {

    }
}
```

### Doctrine ###

#### Classes ####

`sfentityclass`

``` php
use Doctrine\ORM\Mapping as ORM;
use Symfony\Component\Validator\Constraints as Assert;

/**
 * @ORM\Entity(repositoryClass="")
 * @ORM\Table(name="")
 */
class Entity
{
    /**
     * @ORM\Id()
     * @ORM\Column(type="integer")
     * @ORM\GeneratedValue(strategy="AUTO")
     */
    protected $id;
}
```

`sfdocumentclass`

``` php
use Doctrine\ODM\MongoDB\Mapping\Annotations as MongoDB;
use Symfony\Component\Validator\Constraints as Assert;

/**
 * @MongoDB\Document(collection="", repositoryClass="")
 */
class Document
{
    /**
     * @MongoDB\Id()
     */
    protected $id;
}
```

`sfrepository`

``` php
use Doctrine\ORM\EntityRepository;

class EntityNameRepository extends EntityRepository
{
}
```

#### Annotations ####

`sfentity`

``` php
/**
 * @ORM\Entity()
 * @ORM\Table(name="name")
 */
```

`sfidcolumn`

``` php
/**
 * @ORM\Column(name="id", type="integer", nullable=false)
 * @ORM\Id()
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

### Forms ###

`sfform`

``` php
use Symfony\Component\Form\AbstractType;
use Symfony\Component\Form\FormBuilderInterface;
use Symfony\Component\OptionsResolver\OptionsResolverInterface;

class NameType extends AbstractType
{
    /**
     * {@inheritdoc}
     */
    public function buildForm(FormBuilderInterface $builder, array $options)
    {

    }

    /**
     * {@inheritdoc}
     */
    public function setDefaultOptions(OptionsResolverInterface $resolver)
    {
        $resolver->setDefaults(array(
            'data_class' => '',
        ));
    }

    /**
     * {@inheritdoc}
     */
    public function getName()
    {
        return 'name';
    }
}
```

`sfdatatransformer`

``` php
use Symfony\Component\Form\DataTransformerInterface;
use Symfony\Component\Form\Exception\UnexpectedTypeException;
use Symfony\Component\Form\Exception\TransformationFailedException;

class NameTransformer implements DataTransformerInterface
{
    /**
     * {@inheritdoc}
     */
    public function transform($value)
    {

    }

    /**
     * {@inheritdoc}
     */
    public function reverseTransform($value)
    {

    }
}
```

### Twig ###

`sftwigextension`

``` php
class NameExtension extends \Twig_Extension
{
    /**
     * {@inheritdoc}
     */
    public function getFilters()
    {
        return array();
    }

    /**
     * {@inheritdoc}
     */
    public function getTests()
    {
        return array();
    }

    /**
     * {@inheritdoc}
     */
    public function getFunctions()
    {
        return array();
    }
}
```

`sftwigform`

``` jinja
<form class="" action="{{ path('') }}" method="post" {{ form_enctype(form) }}>
    {{ form_errors(form) }}
    {{ form_widget(form) }}
    <input type="submit" value="Submit" />
</form>
```

`trans`

``` jinja
{% trans %}{% endtrans %}
```

### Validation ###

`sfconstraint`

``` php
use Symfony\Component\Validator\Constraint;

/**
 * @Annotation
 */
class NameConstraint extends Constraint
{
    public $message = '';
}
```

`sfconstraintvalidator`

``` php
use Symfony\Component\Validator\Constraint;
use Symfony\Component\Validator\ConstraintValidator;

class NameValidator extends ConstraintValidator
{
    public function validate($value, Constraint $constraint)
    {

    }
}
```

### DependencyInjection ###

`sfdiconfiguration`

``` php
use Symfony\Component\Config\Definition\Builder\TreeBuilder;
use Symfony\Component\Config\Definition\ConfigurationInterface;

class Configuration implements ConfigurationInterface
{
    public function getConfigTreeBuilder()
    {
        $treeBuilder = new TreeBuilder();
        $rootNode = $treeBuilder->root('bundle_name');

        $rootNode
            ->children()
                ->scalarNode('enabled')
                    ->setInfo('Enable the container extension')
                    ->setDefault(true)
                ->end()
            ->end()
        ;

        return $treeBuilder;
    }
}
```

`sfdiextension`

``` php
use Symfony\Component\Config\FileLocator;
use Symfony\Component\DependencyInjection\ContainerBuilder;
use Symfony\Component\DependencyInjection\Loader\XmlFileLoader;
use Symfony\Component\HttpKernel\DependencyInjection\Extension;

class BundleExtension extends Extension
{
    public function load(array $configs, ContainerBuilder $container)
    {
        $config = $this->processConfiguration(new Configuration(), $configs);
        if (false === $config['enabled']) {
            return;
        }

        $loader = new XmlFileLoader($container, new FileLocator(__DIR__.'/../Resources/config'));
        $loader->load('services.xml');
    }
}
```

`sfdiservices`

``` xml
<?xml version="1.0" ?>

<container xmlns="http://symfony.com/schema/dic/services"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://symfony.com/schema/dic/services http://symfony.com/schema/dic/services/services-1.0.xsd">

    <services>
        <service id="id" class="class" />
    </services>
</container>
```

### YAML ###

 `sfroute`

``` yaml
route_name:
    pattern:   /
    defaults:  { _controller: Bundle:Controller:action }
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

# JoshuaEstes/BrowscapBundle

This is a service for you that is similar to the php fucntion get_browser(). It
uses https://github.com/GaretJax/phpbrowscap project.

## Installation

    php composer.phar require joshuaestes/browscap-bundle:0.1.*

This will install the current version which is beta and is the master branch. I
don't want to say it's stable yet until I have some more tests and real world
usage under the belt, but should be good enough to use in a production site.

In your app/AppKernel.php file

    public function registerBundles()
    {
        ...
        $bundles = array(
            ...
            new JoshuaEstes\BrowscapBundle\BrowscapBundle(),
            ...
        );
        ...
    }

## Usage

In your controller, you will just need to get the browser information via the
dependency injection container.

    // @var $browscap \JoshuaEstes\BrowscapBundle\Browscap
    $browscap = $this->container->get('browscap');
    $browser = $browscap->getBrowser();

I have include some help functions to check and see if it's an iPhone, iPad, or
Android. You have access to the following functions.

    // @var $browscap \JoshuaEstes\BrowscapBundle\Browscap
    $browscap = $this->container->get('browscap');
    $browscap->isIPad();
    $browscap->isIPhone();
    $browscap->isAndroid();
    
In the future there might be some more functions.
    

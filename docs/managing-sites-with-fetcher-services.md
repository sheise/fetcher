## Managing Sites with Fetcher Services

To do anything with Fetcher beyond spinning up new sites, you'll need to run a Fetcher Info Site. A Fetcher Info Site is a Drupal site running the [Fetcher Services module](https://www.drupal.org/project/fetcher_services).

A Fetcher Info Site holds records of all your various Drupal projects so that you can build any of your projects using Fetcher. If you manage your projects with a Fetcher Info Site, everyone on your team can spin up or update a local copy of any of your projects with Drush Fetcher.

A company intranet is a good place to install Fetcher Services.

### Setting up a Fetcher Info Site

Fetcher Services module ships with 2 content types: Fetcher Server and Fetcher Site.

#### Fetcher Server

A Fetcher Server contains information about a server on which any of your Fetcher Sites may live. For example a Fetcher Server could be where the staging site of one of your Fetcher Sites is located.


#### Fetcher Site

A Fetcher Site contains infomation about a Drupal site and its various environments which is deployable via fetcher.



### Connecting to a Fetcher Server

To connect to a Fetcher Server, configure your local drushrc.php file with these lines:

```
$options['fetcher']['info_fetcher.class'] = 'FetcherServices\InfoFetcher\FetcherServices';
$options['fetcher']['info_fetcher.config'] = array('host' => 'https://yourfetcherserver.com');
```

`drush fel` (fetcher-list) will give you a list of all the sites it can get info on.

Now you can fetch sites with `drush fetch`.

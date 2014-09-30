CommonSense
===========

### Using Angular's location provider ###

1. Use bower to install it: bower install angular-local-storage --save
2. Use tsd to install the TypeScript definition file: tsd query angularlocalstorage --action install
3. Include the js file in your index.html: <script src="bower_components/angular-local-storage/angular-local-storage.min.js"></script>
4. Add the 'LocalStorageModule' to your angular module and configure its name (in app.ts): angular.module('csWebApp', ['LocalStorageModule'].config(localStorageServiceProvider => { localStorageServiceProvider.prefix = 'ZorgOpDeKaart'; })
5. Inject it into your controller (public static $inject = ['localStorageService']: constructor(private $localStorageService : ng.localStorage.ILocalStorageService) {}
6. Use it (before you set it, check whether you already have it):             
  if ($localStorageService.get('numberOfItems') === null)
    $localStorageService.set('numberOfItems', 25);          // You first need to set the key
  $localStorageService.bind($scope, 'numberOfItems');



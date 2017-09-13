# AngularJS Stock Watchlist Tutorial Application

For now, run `npm install && bower install` then `grunt serve` to get it up and running.

## Overview
TODO

## Prerequisites
TODO

## fixed 

1. get data api  ( quote-service.js)
获取Yahoo股票的API会报错：

http://query.yahooapis.com/v1/public/yql?q=select%20*%20from%20yahoo.finance.quotes%20where%20symbol%20in%20(%27AAPL%27)&format=json&diagnostics=true&env=http://datatables.org/alltables.env

解决方案：改成如下红色字体形式

http://query.yahooapis.com/v1/public/yql?q=select%20*%20from%20yahoo.finance.quotes%20where%20symbol%20in%20(%27AAPL%27)&format=json&diagnostics=true&env=store://datatables.org/alltableswithkeys

2. add stock data watchlist.js

```
      var existingCompany = _.find($scope.companies, function (s) {
          return $scope.newStock.company === s.label;
      });
      if(!existingCompany){
        console.error("can not find company");
        return;
      }
      $scope.watchlist.addStock({
        listId: $routeParams.listId,
        company: existingCompany,
        shares: $scope.newStock.shares
      });
```

3. current can not show chart in dashboard Google charts --dashboard.js

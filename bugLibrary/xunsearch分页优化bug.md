### xunsearch 优化的一个bug

#### 背景

*搜索应用的时候可能会收不到结果，针对收不到结果的情况，需要对搜索词拆拆分、大小写转换能进行二次搜索*

#### bug现象

搜索结果页分页size为25，当搜索结果只有一页数据的时候，当客户端进行下一页请求的时候，这时候是没有搜索结果的，由于二次搜索的判断条件没有针对page做判断，导致程序会对搜索词做二次处理并搜索，此时第二页出现了二次搜索的搜索结果

#### 修正

应该在没有结果进行二次搜索的判断条件中加上分页的判断，当发现不是第一页的时候，没有数据不再进行二次搜索。

#### 代码修正

######修正前

```php
	//$intResultCount 为结果数
	if($intResultCount > 1)
    {
	    //二次搜索
	}
```

######修正前

```php
	//$intResultCount 为结果数
	//$intPage为分页
	if($intResultCount > 1 && $intPage == 1)
    {
	    //二次搜索
	}
```


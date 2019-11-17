![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# POST TITLE
#### SECONDARY TITLE
**TIME STAMP**

## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
你可能需要搜索所有数据库，并查找仅具有特定名称的数据库。也许名称中有数字，但数字彼此不同，因此你不能只使用LIKE编写查询，并提供通配符。你可以做的最好的事情是使用PATINDEX来帮助你获取名称后缀为数字的所有数据库。

假设你的数据库是以INV为前缀的，然后后面是一组数字，所以它看起来像这样：INV #########。

你可以像这样编写查询（The query）：

## English
You might have a need to search across all your databases, and find Databases with ONLY a certain name. Maybe there are numbers in the name, but the number are all different than one another so you can’t just write a query using the LIKE, and provide a wildcard. The best thing you can do is use the PATINDEX to help you get all the Databases that have numbers suffixed on the name.

Lets say you have Databases prefixed with INV, then there are a set of numbers on the end so it looks like this INV#########.

You could write the query like this:

---
## Logic
```SQL
use master;
set nocount on

select
	name
from
	sys.databases
where
	patindex('INV' + '%[0-9]%') > 0
order by
	name asc


```
![#](images/find-database-suffixed-with-numbers.png?raw=true "#")


[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")


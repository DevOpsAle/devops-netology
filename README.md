# devops-netologya
Исключите все файлы с расширением .tfvars, которые могут содержать пароль и идентификатор

Игнорировать файлы *_override.tf *_override.tf.json которые взяты из локальной сети

отслеживать все файлы example_override.tf даже если он попадает под исключение

игнорировать вывод команды: terraform plan -out = tfplan

Игнорировать конфигурационные файлы CLI;
Домашнее задание к занятию «2.4. Инструменты Git»
1) Нашел с помощью команды git log aefea --oneline
выдал неполный хеш с комитом "aefead220 Update CHANGELOG.md"
затем с помощью git log aefead220
полчил результат полного commit "aefead2207ef7e2aa5dc81a34aedf0cad4c32545"

2) git log 85024d3
В результате мы видем полный commit 85024d3100126de36331c6982bfaac02cdab9e76
а так же к какому tag он пренодлежит v0.12.23

3) git log b8d720 --oneline
Мы нашли полный хеш b8d720f83
дальше  git log b8d720f83
видем результат где есть полное имя commita
а так же видем 2 merge 56cd7859e 9ea88f22f
по котрым мы можем дальше выяснить откуда взялся наш хеш
с помощью команд git log 56cd7859e появился новый merge ffbcf5581
из этого следует вывод что у него 3 родителя

5)C помощью команды  git log --pretty=oneline -S "func providerSource"
5af1e6234ab6da412fb8637393c5a17a1b293663
8c928e83589d90a031f811fae52a81be7153e82f
Потом используем git show что бы посмотреть содержание
Тем самым можно предположить сама функция была сделана 8c928e
а 5af1e6 тут ее подправили

6) git log -L :globalPluginDirs:plugins.go
мы нашли все commit где были изменения
78b12205587fe839f10d946ea3fdc06719decb05
52dbf94834cb970b510f2fba853a5b49ad9b1a46
41ab0aef7a0fe030e84018973a64135b11abcd70

7)git log -SsynchronizedWriters
 Martin Atkins

4)

 c помощью git log v0.12.23..v0.12.24
 мы можем посмотреть все commit и хеши котрые были сделаны
commit 33ff1c03bb960b332be3af2e333462dde88b279e (tag: v0.12.24)
Author: tf-release-bot <terraform@hashicorp.com>
Date:   Thu Mar 19 15:04:05 2020 +0000

    v0.12.24

commit b14b74c4939dcab573326f4e3ee2a62e23e12f89
Author: Chris Griggs <cgriggs@hashicorp.com>
Date:   Tue Mar 10 08:59:20 2020 -0700

    [Website] vmc provider links

commit 3f235065b9347a758efadc92295b540ee0a5e26e
Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>
Date:   Thu Mar 19 10:39:31 2020 -0400

    Update CHANGELOG.md

commit 6ae64e247b332925b872447e9ce869657281c2bf
Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>
Date:   Thu Mar 19 10:20:10 2020 -0400

    registry: Fix panic when server is unreachable

    Non-HTTP errors previously resulted in a panic due to dereferencing the
    resp pointer while it was nil, as part of rendering the error message.
    This commit changes the error message formatting to cope with a nil
    response, and extends test coverage.

    Fixes #24384

commit 5c619ca1baf2e21a155fcdb4c264cc9e24a2a353
Author: Nick Fagerlund <nick.fagerlund@gmail.com>
Date:   Wed Mar 18 12:30:20 2020 -0700

    website: Remove links to the getting started guide's old location

    Since these links were in the soon-to-be-deprecated 0.11 language section, I
    think we can just remove them without needing to find an equivalent link.

commit 06275647e2b53d97d4f0a19a0fec11f6d69820b5
Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>
Date:   Wed Mar 18 10:57:06 2020 -0400

    Update CHANGELOG.md

commit d5f9411f5108260320064349b757f55c09bc4b80
Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>
Date:   Tue Mar 17 13:21:35 2020 -0400

    command: Fix bug when using terraform login on Windows

commit 4b6d06cc5dcb78af637bbb19c198faff37a066ed
Author: Pam Selle <pam@hashicorp.com>
Date:   Tue Mar 10 12:04:50 2020 -0400

    Update CHANGELOG.md

commit dd01a35078f040ca984cdd349f18d0b67e486c35
Author: Kristin Laemmert <mildwonkey@users.noreply.github.com>
Date:   Thu Mar 5 16:32:43 2020 -0500

    Update CHANGELOG.md

commit 225466bc3e5f35baa5d07197bbc079345b77525e
Author: tf-release-bot <terraform@hashicorp.com>
Date:   Thu Mar 5 21:12:06 2020 +0000

    Cleanup after v0.12.23 release



---
tags: ["kovri"]
terms: ["Tunnel", "Tunnels", "туннелям", "туннельным", "туннельное", "туннельные", "туннель", "туннельное-шифрование", "туннели", "туннелю", "туннeльные", "туннеля", "туннельным", "туннельное", "туннелям"]
summary: "Однонаправленные виртуальные сети, которые передают сообщения через определенную последовательность I2P маршрутизаторов"
---

### Основная информация

Когда вы связываетесь по @I2P (посетите @Eepsite / используйте @чесночную-службу), вам, прежде всего, необходимо соединиться с одноранговым узлом, используя @транспорты, а затем построить виртуальные *туннели*. Эти виртуальные туннели являются временными, однонаправленными путями передачи информации в порядке определённой последовательности @I2P маршрутизаторов к адресу @назначения. Туннели сначала строятся, а затем используются при помощи @чесночного-шифрования и являются универсальным механизмом передачи всех @I2NP @сообщений.

Каждый одноранговый узел строит как минимум *два* однонаправленных туннеля: один предназначен для **выходного трафика**, а другой — для **входящего трафика**. Эти туннели классифицируются либо как **входящие туннели** (когда @сообщения передаются в направлении создателя туннеля), либо как **выходящие туннели** (когда создатель туннеля отправляет @сообщения в направлении от себя). Таким образом, для кругового прохождения @сообщения и получения ответа по вашему адресу @назначения необходимо *четыре туннеля* (два для вас и два для адреса назначения).

### Углублённая информация

From @Java-I2P:

>
В сети I2P @сообщения передаются в одном направлении по виртуальному туннелю между одноранговыми узлами, при этом используются доступные средства, позволяющие @сообщению пройти до следующего транзитного участка. Сообщения принимаются в шлюз @туннеля, связываются и / или фрагментируются в сообщения туннеля фиксированного размера, после чего направляются до следующего транзитного участка туннеля, где происходит обработка и верифицируется действительность @сообщения, после чего оно отправляется на следующий транзитный участок и так далее, до тех пор, пока оно не достигнет конечной точки @туннеля. В этой точке сообщения связываются шлюзом и направляются в соответствии с инструкцией: либо другому маршрутизатору, в другой туннель на другой маршрутизатор, либо локально.

>
Все туннели работают одинаково, но их можно разбить на две разные группы: входящие и выходящие туннели. У входящих туннелей ненадёжный шлюз пропускает сообщения к создателю туннеля, который и является конечной точкой туннеля. В случае с выходящими туннелями их создатель служит шлюзом, пропускающим сообщения к удалённой точке.

>
Создатель туннеля выбирает те узлы, которые будут входить в состав туннеля, и обеспечивает каждого из них необходимыми данными конфигурации. Количество транзитных участков может быть любым. Это делается для того, чтобы другим участникам или третьей стороне было сложно определить длину туннеля, или же даже для того, чтобы сговаривающиеся участники не могли вообще определить, являются ли они участниками одного и того же туннеля (это исключает возможность возникновения ситуации, когда сговорившиеся узлы оказываются в сети рядом друг с другом).

### Примечания

Из статьи @Java-I2P:

>
@I2P является пакетной коммутируемой сетью даже с учётом наличия этих туннелей, что позволяет пользоваться преимуществом использования множества туннелей, работающих параллельно. Это повышает устойчивость сети и сбалансированность нагрузки. Даже несмотря на то, что I2P туннели напоминают сеть с коммутацией каналов, всё в I2P строго завязано на сообщениях — туннели являются просто ухищрением, позволяющим организовать доставку сообщений. Нет никаких условий, касающихся надёжности или порядка сообщений, а ретрансляция происходит на более высоких уровнях (например, потоковой библиотеки клиентского уровня I2P).

### Документация

Спецификации и подробную документацию можно найти на страницах [туннельная маршрутизация](https://geti2p.net/en/docs/how/tunnel-routing) и [реализация туннелей](https://geti2p.net/en/docs/tunnels/implementation).
### Виртуальная машина ядра
  * KVM (для виртуальной машины на основе ядра) — это полное решение виртуализации для Linux на оборудовании x86, содержащее расширения виртуализации (Intel VT или AMD-V).
    Он состоит из загружаемого модуля ядра, kvm.ko, который обеспечивает базовую инфраструктуру виртуализации, и модуля, специфичного для процессора, kvm-intel.ko или kvm-amd.ko.
    Используя KVM, можно запускать несколько виртуальных машин с немодифицированными образами Linux или Windows.
    Каждая виртуальная машина имеет собственное виртуализированное оборудование: сетевую карту, диск, графический адаптер и т. д.
    KVM — это программное обеспечение с открытым исходным кодом. Компонент ядра KVM включен в основную версию Linux с версии 2.6.20.
    Компонент пользовательского пространства KVM включен в основную ветку QEMU с версии 1.3.
    Блоги людей, занимающихся разработкой виртуализации, связанной с KVM, собраны на http://planet.virt-tools.org/.

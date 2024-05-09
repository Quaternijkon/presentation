由于rCore的接口较老，需要使用较旧版本的virtio-drivers，所以对于系统测试，另写了一版针对较旧版本的virtio-drivers实现的块设备驱动程序。
# 单元测试
位于 `pre/virtio-drivers/src/device/blk.rs` 中， 进入`virtio-drivers`目录，终端运行`cargo test`。

# 集成测试
位于 `pre/virtio-drivers/examples/riscv/src/main.rs`,该程序在qemu中模拟各种设备，其块设备驱动使用了上述的块设备驱动程序。

# 系统测试
进入 `pre/rCore-Tutorial-v3/os`目录，运行`make run`，即可运行rCore操作系统，其使用了上述的块设备驱动程序。

# TODO:Alien系统测试
从理论上分析了其可行性，比如其接口与virtio-driver一致，但难点在于和块设备驱动耦合的模块较多，且测试程序编写较裸机测试程序难。
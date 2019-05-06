# mvvm
  双向数据绑定
var vm = {}
        var data = {
            name: 'zhangsan',
            age: 20
        }

        var key, value
        for (key in data) {
            (function (key) {
                Object.defineProperty(vm, key, {
                    get: function () {
                        console.log('get', data[key]) // 监听
                        return data[key]
                    },
                    set: function (newVal) {
                        console.log('set', newVal) // 监听
                        data[key] = newVal
                    }
                })
            })(key)
        }
vm.name=123;vm.name

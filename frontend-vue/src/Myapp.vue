<template>
    <!-- 在 HTML 文件中的 head 部分引入 Bootstrap CSS -->

    <head>
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    </head>

    <div class="vertical-container">
        <div>
            <nav class="navbar navbar-expand-lg navbar-light bg-light container-fluid">
                <div class="container">
                    <!-- Navbar品牌标志 -->



                    <!-- 导航链接、表单和其他内容 -->
                    <div class="collapse navbar-collapse" id="navbarNav">

                        <ul class="navbar-nav">
                            <!-- 导航链接 -->
                            <!-- <li class="nav-item">
                            <a class="nav-link" href="#">Home</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#">About</a>
                        </li> -->
                            <!-- 按钮 -->
                            <li class="nav-item">
                                <button @click="toggleComponentA" class="btn btn-secondary">Publications</button>
                            </li>
                            <li class="nav-item">
                                <p> &nbsp; </p>
                            </li>
                            <li class="nav-item" style="width: 200px; ">
                                <button @click="toggleComponentB" class="btn btn-secondary">Papers of years</button>
                            </li>
                            <li class="nav-item">
                                <p> &nbsp; </p>
                            </li>
                            <li class="nav-item">
                                <button class="btn btn-secondary">Button1</button>
                            </li>
                            <li class="nav-item">
                                <p> &nbsp;&nbsp; </p>
                            </li>
                            <li style="width: 200px; ">
                                <!-- 搜索类型的勾选框 -->
                                <label style="align-items: center;" for="exampleDropdown">检索项目:</label>
                                <select v-model="searchType" name="exampleDropdown">
                                    <option value="Author">查询作者作品</option>
                                    <option value="Publication">出版物</option>
                                    <option value="Coauthor">查询共同作者</option>
                                    <!-- Add more options as needed -->
                                </select>
                                <p>{{ searchType }}</p>

                            </li>
                            <li class="nav-item">
                                <!-- 搜索框 -->
                                <input type="text" v-model="searchQuery" placeholder="Search...                 " />
                            </li>
                            <li class="nav-item">
                                <p> &nbsp; </p>
                            </li>
                            <li class="nav-item">
                                <!-- 搜索按钮 -->
                                <button class="btn btn-primary" @click="handleSearch">Search</button>
                            </li>
                        </ul>
                    </div>
                </div>

            </nav>
        </div>
        <div>
            <!-- 使用动态组件来渲染不同的子组件 -->
            <component :is="currentComponent"></component>
        </div>
    </div>
</template>
  
<script>
import ComponentA from './components/ComponentA.vue';
import ComponentB from './components/ComponentB.vue';

export default {
    data() {
        return {
            // 设置初始渲染的组件为 ComponentA
            currentComponent: null,
            searchType: 'Author', // 默认搜索类型
            searchQuery: '', // 搜索框输入内容
        };
    },
    methods: {
        toggleComponentA() {
            // 切换当前渲染的组件
            this.currentComponent = ComponentA;
        },
        toggleComponentB() {
            // 切换当前渲染的组件
            this.currentComponent = ComponentB;
        },
        handleSearch() {
            // 处理搜索逻辑，根据 this.searchType、this.searchQuery 进行搜索
            console.log('Search Query:', this.searchQuery);
            console.log('Search Type:', this.searchType);
        },
    },
    components: {
        ComponentA,
        ComponentB
    }
};
</script>

<style scoped>
/* 样式可以根据需要自行修改 */
.vertical-container {
    display: flex;
    flex-direction: column;
    height: 100vh;
}

.navbar {
    background-color: #f8f9fa;
}

.form-check-label {
    margin-left: 8px;
}

/* 自定义搜索框宽度 */
.custom-search-input {
    width: 300px;
    /* 根据需要设置宽度 */
}
</style>

  
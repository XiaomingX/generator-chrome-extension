# Chrome 扩展生成器

> 该生成器提供了开发 Chrome 扩展所需的所有基础结构。您可以选择浏览器 UI 类型（浏览器操作、页面操作、地址栏输入）并根据需要配置权限。

## 快速开始

1. **安装必要的全局工具**：

   ```sh
   npm install --global yo gulp-cli bower
   ```

2. **安装 Chrome 扩展生成器**：

   ```sh
   npm install -g generator-chrome-extension
   ```

3. **创建并进入新目录**：

   ```sh
   mkdir my-new-chrome-extension && cd $_
   ```

4. **生成新项目**：

   ```sh
   yo chrome-extension
   ```

5. **编译 ES2015 代码**：

   ```sh
   gulp babel
   ```

6. **启用实时监视以自动编译**：

   ```sh
   gulp watch
   ```

7. **构建生产版本的扩展**：

   ```sh
   gulp build
   ```

## 测试 Chrome 扩展

在 Chrome 浏览器中，打开 `chrome://extensions`，启用开发者模式，然后加载未打包的扩展进行测试。

## 可用的生成器

- **chrome-extension**：设置一个新的 Chrome 扩展项目，生成所有必要的基础文件。

   ```bash
   yo chrome-extension
   ```

## Gulp 任务

### Babel 转码

生成器支持通过 Babel 转换 ES2015 语法。开发过程中，修改代码后需要运行以下命令进行转码：

```sh
gulp babel
```

### 实时监视（Watch）

实时监视任务可以自动编译源代码并重新加载扩展。

```bash
gulp watch
```

**注意**：启动 `gulp watch` 后，需要重新加载扩展以激活实时重载功能。对于内容脚本，需要刷新其应用的页面。

### 构建和打包

构建应用程序，生成的生产版本将位于 `dist` 目录中：

```bash
gulp build
```

要将项目压缩为 `.zip` 文件以便在 Chrome Web Store 上发布：

```bash
gulp package
```

## 选项

- `--no-babel`：如果不希望使用 [Babel](https://babeljs.io/) ES2015 转码器。

- `--skip-install`：跳过在脚手架完成后自动执行 `bower` 和 `npm`。

- `--test-framework=[framework]`：默认为 `mocha`，可切换为其他支持的测试框架，如 `jasmine`。

- `--sass`：添加对 [Sass](http://sass-lang.com/libsass) 的支持。

- `--all-permissions`：显示 Chrome 扩展的所有权限。

## ES2015 和 Babel

默认情况下，生成器支持 ES2015 语法。由于 Chrome 尚未完全支持所有 ES2015 功能，需要使用 `gulp babel` 进行转码。源代码位于 `scripts.babel` 目录，转码后的代码位于 `scripts` 目录。

如果不想使用 Babel 和 ES2015，可在初始化项目时添加 `--no-babel` 选项：

```sh
yo chrome-extension --no-babel
```

## Sass 支持

通过 `--sass` 选项，生成器支持 Sass，并在 `styles.scss` 中生成样板文件。可使用以下命令编译为 CSS：

```sh
yo chrome-extension --sass
```

## 全部权限

需要为 Chrome 扩展添加更多权限？使用 `--all-permissions` 选项查看完整权限列表：

```sh
yo chrome-extension --all-permissions
```

**注意**：请根据最新的 [generator-chrome-extension](https://github.com/yeoman/generator-chrome-extension) 文档确认上述信息的准确性。 
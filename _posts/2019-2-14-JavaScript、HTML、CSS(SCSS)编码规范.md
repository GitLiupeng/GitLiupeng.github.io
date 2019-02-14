# JavaScript/HTML/CSS/SCSS编码规范

## 代码风格规范

### Prettier介绍

* Prettier是一个代码格式化工具

* 支持JavaScript、JSX、Angular、Vue、Flow、TypeScript、CSS/Less/SCSS、HTML、JSON、GraphQL、Markdown、YAML

* 去掉所有原始代码格式，并确保输出的代码风格完全一致

### Prettier安装

* 新版WebStorm自带Prettier，但是需要安装npm包并配置

* npm init

* npm i -D prettier

* WebStorm配置：File > Setting > Tools > File Watchers > prettier

* 文件保存时自动格式化代码

* npm i -g prettier

* 配置全局路径：File > Settings > Languages & Frameworks > JavaScript > Prettier


## JavaScript规范

### SonarJS

* [Sonar JavaScript规则](https://rules.sonarsource.com/javascript)

* 可使用SonarLint插件，但不能在代码里自动提示

### ESLint

* [ESLint规则](https://eslint.org/docs/rules/)

* 可配置成Sonar规则，虽然是Sonar官方ESLint配置，但是感觉不完整，[eslint-plugin-sonarjs](https://github.com/SonarSource/eslint-plugin-sonarjs)

* 也有现成的standard规则，[JavaScript standard 代码规范](https://standardjs.com/rules-zhcn.html)

* WebStorm可启用ESLint自动提示

### ESLint安装

* 全局安装：npm i -g eslint

* 启用ESLint：File > Settings > Languages & Frameworks > JavaScript > Code Quality Tools > ESLint

* ESLint与Prettier结合：npm i -D eslint eslint-config-prettier eslint-plugin-prettier

* SonarJS规则配置：

    * npm i -D eslint-plugin-sonarjs

    * 项目根目录新建文件.eslintrc

    * 文件内容：
    
    <pre>
        {
            "env": {
                "browser": true,
                "jquery": true
            },
            "extends": ["plugin:sonarjs/recommended", "plugin:prettier/recommended"],
            "plugins": ["sonarjs", "prettier"],
            "parserOptions": {
                "ecmaVersion": 5
            }
        }
    </pre>

* StandardJS规则配置(推荐)：

    * npm i -D eslint-plugin-standard
    
    * .eslintrc文件内容：
    
    <pre>
        {
            "env": {
                "browser": true,
                "jquery": true
            },
            "extends": ["standard", "plugin:prettier/recommended"],
            "parserOptions": {
                "ecmaVersion": 5
            }
        }
    </pre>

## HTML规范

### SonarHTML

* [Sonar HTML规则](https://rules.sonarsource.com/html)

* 暂未发现对应工具

### HTMLHint

* [HTMLHint规则](https://github.com/htmlhint/HTMLHint/wiki/Rules)

* [HTMLHint使用](https://github.com/htmlhint/HTMLHint/wiki/Usage)

* 不能自动提示，只能用命令行

### WebStorm

* WebStorm规则：File > Settings > Editor > Inspections > HTML

* 可以自动提示

* 推荐直接使用WebStorm自带的HTML规则结合Prettier使用

## CSS/SCSS规范

### SonarCSS

* [Sonar CSS规则](https://rules.sonarsource.com/css)

* 暂未发现对应工具

### StyleLint

* [StyleLint规则](https://stylelint.io/user-guide/rules/)

* 可结合WebStorm使用，自动提示

* StyleLint安装：npm i -g stylelint 

* WebStorm配置:

    * File > Settings > Languages & Frameworks > Stylesheets > Stylelint

    * File > Settings > Editor > Inspections > CSS > Code quality tools > Stylelint

* standard规则配置：
    
    * npm i -D stylelint-config-standard
    
    * 项目根目录新建文件.stylelintrc
    
    * 文件内容：
    
    <pre>
        {
          "extends": "stylelint-config-standard"
        }
    </pre>
    
## 总结

* 公司要用Sonar代码质量管理平台，但是Sonar没有对应自动提示的工具，所以自己配置了一套

* 本地代码按照lint工具改完后，提交到Sonar应该不会再检测出大问题

* 没必要记规则，保存代码直接符合风格规范，出现质量问题跟着提示一个个改就OK了
    
    




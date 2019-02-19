# JavaScript/HTML/CSS/SCSS编码规范

## 代码风格规范

### Prettier介绍

* [Prettier官网](https://prettier.io/)

* Prettier是一个代码格式化工具

* 支持JavaScript、JSX、Angular、Vue、Flow、TypeScript、CSS/Less/SCSS、HTML、JSON、GraphQL、Markdown、YAML

* 去掉所有原始代码格式，并确保输出的代码风格完全一致

### Prettier安装

* 新版WebStorm自带Prettier，但是需要安装npm包并配置

* npm init

* npm i -D prettier

* WebStorm配置：File > Setting > Tools > File Watchers > prettier

* 文件保存时自动格式化代码

* npm i -D prettier

* 配置路径：File > Settings > Languages & Frameworks > JavaScript > Prettier


## JavaScript规范

### SonarJS

* [Sonar JavaScript规则](https://rules.sonarsource.com/javascript)

* 可使用SonarLint插件，WebStorm: File > Setting > Plugins 搜索SonarLint，安装完需重启WebStorm

* SonarLint配置：

   * File > Settings > Other Settings > SonarLint General Settings 添加SonarQube servers并启用自动检测
   
   * SonarQube URL: http://www.airuima.net:8000
   
   * File > Settings > Other Settings > SonarLint Project Settings 绑定server和project并启用配置

### ESLint

* [ESLint规则](https://eslint.org/docs/rules/)

* 可配置成Sonar规则，虽然是Sonar官方ESLint配置，但是感觉不完整，[eslint-plugin-sonarjs](https://github.com/SonarSource/eslint-plugin-sonarjs)

* 也有现成的standard规则，[JavaScript standard 代码规范](https://standardjs.com/rules-zhcn.html)

* WebStorm可启用ESLint自动提示

### ESLint安装

* npm i -D eslint eslint-plugin-import eslint-plugin-node eslint-plugin-promise

* 启用ESLint：File > Settings > Languages & Frameworks > JavaScript > Code Quality Tools > ESLint

* File > Settings > Editor > Inspections > JavaScript > Code quality tools > ESLint

* ESLint与Prettier结合：npm i -D eslint-config-prettier eslint-plugin-prettier

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

    * npm i -D eslint-plugin-standard eslint-config-standard
    
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

* 可配置成推荐的standard规则，[stylelint-config-standard](https://github.com/stylelint/stylelint-config-standard)

* 可结合WebStorm使用，自动提示

* StyleLint安装：npm i -D stylelint 

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

* 公司要用Sonar代码质量管理平台，但是SonarLint只能检测JS，可以配置成线上的规则

* JS本地SonarLint提示的问题和线上一致，同时启用ESLint双重保障，再加上Prettier自动美化代码

* HTML lint工具只能用命令行，太麻烦，决定弃用，使用WebStorm自带的规则检测

* CSS/SCSS 使用Stylelint检测，使用官方推荐的配置，无需手动添加一条条规则

* 没必要记规则，保存代码直接符合一致的风格规范，出现质量问题跟着提示一个个改就OK了
    
* 为了方便，总结一下配置：

1. File > Setting > Plugins 下载安装SonarLint插件

2. File > Settings > Other Settings > SonarLint General Settings 添加SonarQube servers并启用自动检测

3. SonarQube URL: http://www.airuima.net:8000
   
4. File > Settings > Other Settings > SonarLint Project Settings 绑定server和project并启用配置

5. npm init

6. npm i -D prettier eslint stylelint eslint-plugin-import eslint-plugin-node eslint-plugin-promise eslint-config-prettier eslint-plugin-prettier eslint-plugin-standard eslint-config-standard stylelint-config-standard
    
7. File > Setting > Tools > File Watchers > prettier 添加Prettier支持的文件

8. File > Settings > Languages & Frameworks > JavaScript > Prettier 启用Prettier

9. File > Settings > Languages & Frameworks > JavaScript > Code Quality Tools > ESLint 启用ESLint

10. File > Settings > Editor > Inspections > JavaScript > Code quality tools > ESLint

11. File > Settings > Editor > Inspections > HTML 配置HTML规则

12. File > Settings > Languages & Frameworks > Stylesheets > Stylelint 启用Stylelint

13. File > Settings > Editor > Inspections > CSS > Code quality tools > Stylelint

14. 添加ESLint配置文件.eslintrc

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

15. 添加Stylelint配置文件.stylelintrc

  <pre>
      {
        "extends": "stylelint-config-standard"
      }
  </pre>
  
* 最后，由于用JS写的项目大部分都是以前的项目，不会用到 ES6+ 新语法，可将WebStorm自带的检测改为ES5，不然用var定义变量都会提示有问题

  * File > Settings > Languages & Frameworks > JavaScript 选择版本为ECMAScript 5.1



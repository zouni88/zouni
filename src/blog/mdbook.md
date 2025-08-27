## mdbook: book文档书写工具：rust-lang 官方出品
https://github.com/rust-lang/mdBook

### 支持mermaid 插件 安装
> cargo install mdbook-mermaid  

### 这一步会下载 mermaid相关js文件
> mdbook-mermaid install .  

### book.toml中添加如下
```toml
[preprocessor.mermaid]
command = "mdbook-mermaid"

[output.html]
additional-js = ["mermaid.min.js", "mermaid-init.js"]
```
- **Cài đặt**  
    ```
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
    ```   
    - Các plugin hay dùng  
      ``` 
      git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions

      git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
      ``` 
    - Enable plugin
        + Mở ~/.zshrc
        + Sửa plugins=(git) thành **plugins=(git zsh-autosuggestions zsh-syntax-highlighting)**
        + ![image](/image/zshrc.png)

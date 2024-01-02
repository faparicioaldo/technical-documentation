Install
===============
This section describes the process to install sphinx

Steps

https://docs.readthedocs.io/en/latest/intro/getting-started-with-sphinx.html

python3 

pip install sphinx
pip install sphinx_rtd_theme

mkdir technical-documentation
cd technical-documentation
sphinx-quickstart
make html


issues 

sphinx-quickstart command not found

look the location 
  find $HOME -name sphinx-quickstart
  /home/aldo/.local/bin/sphinx-quickstart

add to the init file
  echo 'export PATH="/home/aldo/.local/bin:$PATH"' >> ~/.zshrc

apply changes
  source ~/.zshrc

now it should work 
  sphinx-quickstart


https://www.youtube.com/watch?v=vFAkt_N6yuk&list=PLPDCBPbzk1AYghqYazE7Cxt3p7edml8I7&index=1


nvchad - nvim
  - java
    lombok
    telescope
    see packages as eclipse
oh-my-tmux - tmux
  - create detached from files
  - persists sessions, windows and panels
  - 
fzf
lua





---
title: Japanese input in openSUSE Tumbleweed's KDE
date: 2024-01-15
summary: "Here are the steps to install **fcitx5** and **fcitx5-mozc** input method for Japanese in **openSUSE Tumbleweed**."

categories:
    - Japanese
tags:
    - openSUSE
    - KDE
---

# Situation

Las year after a pretty bad blackout I decided to test the native BTRFS backups from openSUSE Tumbleweed and changed from Ubuntu 22.10 on my personal laptop. The wonderful thing about change is that always brings learning with it but on the forums was mostly GNOME. 

Here are the steps to install **fcitx5** and **fcitx5-mozc** input method for Japanese in **openSUSE Tumbleweed**:

# Solution

Open the terminal and enter the following command to install **fcitx5** and **fcitx5-mozc**[^1]:

   ```shell
   sudo zypper install fcitx5-mozc
   ```

 Next, if you aren't using a desktop environment [^2] you may need to configure the input method. To do this, create or open a new file called `~/.profile` and add the following lines to it:

   ```bash
   export GTK_IM_MODULE=fcitx
   export QT_IM_MODULE=fcitx
   export XMODIFIERS=@im=fcitx
   ```

 Save the file and restart your system.

 Once you have restarted your system, open the **fcitx5 configuration tool** by running the following command in the terminal:

   ```bash
   fcitx5-configtool
   ```

In the configuration tool, click on the **Input Method** tab and then click on the **+** button to add a new input method.

Select **Mozc** from the list of input methods and click on the **Add** button.

You can now switch to the **Mozc** input method by pressing the **Ctrl + Space** keys.

Let me know if you have any questions.

# References

Photo by <a href="https://unsplash.com/@frederickjmedina?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Frederick Medina</a> on <a href="https://unsplash.com/photos/person-holding-brown-bread-with-yellow-sliced-fruit-6SWHWcLyD-8?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>

[^1]: Japanese input in plasma 5.8 kde <https://forums.opensuse.org/t/japanese-input-in-plasma-5-8-kde/125211>
[^2]: Localization/Japanese - ArchWiki. <https://wiki.archlinux.org/title/Localization/Japanese>.





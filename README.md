CI build tools need a predicatable version of Chrome so that the chromedriver version keeps working.

This .deb distribution can be insatlled to provide a known version of chrome.

These lines in a github build file will install it:

      - name: Fetch chrome source
        run: sudo wget -0 spec/chrome_amd64.deb https://github.com/passinc-ltd/chrome/chrome_114_amd64.deb
      - name: Install chrome from source
        run: sudo dpkg -i spec/chrome_amd64.deb
      - name: Chrome version
        run: google-chrome --version


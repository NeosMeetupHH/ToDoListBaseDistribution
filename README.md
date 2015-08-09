# ToDoList Example Application

> This example will show how to use TypoScript 2.0 in a context outside of Neos.

## How to install

1. Clone this repository and run `composer install`.

  ```bash
  git clone https://github.com/NeosMeetupHH/ToDoListBaseDistribution
  cd ToDoListBaseDistribution
  composer install
  ```
2. If you're using apache, create a virtualhost with a document root pointing to the /Web directory that was created during composer installation. Use the corresponding mechanisms for other web servers if needed.
3. Create a (MySQL) database for the application.

  ```SQL
  CREATE DATABASE todolist COLLATE utf8_unicode_ci;
  ```

4. Configure Flow to use the database, therefore create the file Configuration/Development/Settings.yaml:

  ```yaml
  TYPO3:
    Flow:
      persistence:
        backendOptions:
          dbname: 'todolist'   # your database name
          user: ''             # your database user
          password: ''         # your database password
  ```

5. Run all doctrine migrations to install the basic database structure:

  ```bash
  ./flow doctrine:migrate
  ```

6. Run the fixture installation command, to make sure there's initial data in your database:

  ```bash
  ./flow todolist:fixtures
  ```

Now, the application should be ready to run.

## Credits

This demo application is powered by [Flow](https://github.com/Inkdpixels/Brics/releases).

The frontend part was done with [reduct](https://github.com/reduct) and [Brics](https://github.com/Inkdpixels/Brics).

Have a look at all three of them, these are powerful companions ;)

## License

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

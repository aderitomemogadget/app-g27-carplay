Aplicação HiQi
=============


Requisitos:
-----------

É necessário usar uma consola Shell, no Windows pode ser a "Windows PowerShell".
Previamente também ter instalado as seguintes frameworks:

* Node.js (https://nodejs.org/en/)
* git (https://git-scm.com/download/win)


# Guia a seguir para fazer migração de Phonegap => Ionic (apenas para iOS, Android continua a ser por Phonegap)

https://ionicframework.com/docs/appflow/cookbook/phonegap-build-migration

# Explicação da Estrutura da Aplicação HiQi

A aplicação HiQi é sub-dividida em 2 partes, uma componente **Server-Side(PHP)** e outra componente **Client-Side(JS/HTML)**.

### Na componente Server-Side(PHP) refere a todo comportamento da app a nível de:

* Backoffice (https://app.g27.eu/admin)
* Estrutura da Plataforma (por ftp, dentro de admin/)

	* **login.php** (referente a login)
	* **info.php** (referente a páginas de informação)
	* **maps.php** e **location.php** (referente a google maps)
	* **actions.php** (um dos ficheiros principais onde se pode encontrar a maior parte das acções)
	* **pagamentos.php** (igualmente importante como o anterior, mas referente a pagamentos)

* Webservices (admin/webservices)

	* **postos.json** (ficheiro gerado de hora em hora com os postos da GASODATA)
	* **gasodata.php** (ficheiro de integração com a GASODATA)
	* **ws_cards.php** (ficheiro de integração com o NAV - Hydra)
	* **sms.php** (ficheiro de integração com o sistema de sms (https://www.4movel.com/))


### Na componente Client-Side(JS/HTML) temos a arquitectura da app, isto é:

* **ANDROID**

	* **css** (folhas de estilos da app)
	* **res** (icons e screens)
	* **js** (toda a arquitectura da aplicação)

		* app_sync.js (estrutura da app e integração com cordova)
		* app.js (estrutura do fluxo da app)
		* helpers.js (ficheiro auxiliar ao app.js, onde é possível encontrar a ligação com a APP e o Servidor (Pedidos AJAX))
		* filter_destroy.js (traduções)

* **iOS**
	
	* **config.xml** (configurações específicas de iOS)
	* **plugins** (configurações de plugins necessários para um bom funcionamento da app em iOS)
	* **resources** (icons e screens)
	* **www** (toda a app com o mesmo aspecto que a de ANDROID)
# Integracao-Opencart-3.0-e-Bling
Integração Opencart 3.0 e Bling


Parta a instalação basta  subistituir  os arquivos  dentro do Opencart  3.0

É necessário alterar a APYKEY do arquivo catalog/model/catalog/product.php



	public function blingCURL($url,$parametros = array("imagem"=>"S")){
		$params = array(
			"apikey"=>" DIGITE SUA APIKEY AQUI"
		);

		$params = $params + $parametros;
		
		
		$curl_handle = curl_init();
		curl_setopt($curl_handle, CURLOPT_URL, $url . '?' . http_build_query($params));
		curl_setopt($curl_handle, CURLOPT_RETURNTRANSFER, TRUE);
		$response = curl_exec($curl_handle);
		curl_close($curl_handle);
		return json_decode($response,true);
	}

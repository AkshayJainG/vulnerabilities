
<p> 自分のアプリケーション間でのみデータを共有するアクティビティを使用している場合、「android：protectionLevel」属性を使用し、「署名」を保護に設定することをお勧めします。  署名 のパーミッションはユーザー確認を必要としないため、アクティビティにアクセスするアプリが同じ鍵で署名されている場合、より優れたユーザエクスペリエンスとサービスへのより制御されたアクセスを提供します。</p>
 <p>   もしアクティビティがそれ自体の中で呼び出された時は、それをエクスポート、あるいはカスタム権限のインテントフィルタを使用しないでください。 </p>


応答がHTTPS経由で提供されると、Webサーバーとの接続はTLSで暗号化されるため、スニッファーや中間者攻撃から保護されます。
HTTPSレスポンスに、通常の平文HTTPで取得されたコンテンツへのリンクが含まれている場合、接続は部分的にのみ暗号化されます。暗号化されていないコンテンツはスニッファーにアクセス可能で、中間者攻撃の攻撃者が変更できるため、接続は保護されません。

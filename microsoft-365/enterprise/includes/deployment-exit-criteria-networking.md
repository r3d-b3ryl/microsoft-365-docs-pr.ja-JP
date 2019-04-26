<a name="crit-networking-step1"></a>
### <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a>必須: Microsoft 365 Enterprise に必要なネットワーク環境が準備できていること

- オフィスごとの、Office 365、Microsoft Intune、Windows 10 Enterprise のインストールと更新を含む、Microsoft 365 トラフィックに見合ったインターネット帯域幅の確保
- Office 365 の参照アーキテクチャに関するネットワーク全体のマップ
- パイロット版としてテストされた、トラフィックの待機時間の要件を満たすネットワーク変更

必要に応じて、[手順 1](../networking-provide-bandwidth-cloud-services.md) がこの必須条件を満たす上で役立ちます。

<a name="crit-networking-step2"></a>
### <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a>必須: 支店のローカル インターネット接続と名前解決機能

各支店に、ローカル ISP を使用したインターネット アクセスが構成され、そのローカル ISP の DNS サーバーがローカル パブリック IP を使用してインターネット上での自身の位置を識別するようになっていること。これにより、Office 365 と Intune にアクセスするユーザーのパフォーマンスを最大限に引き出すことができます。

各支店でローカル ISP を使用していない場合、ネットワーク トラフィックが組織のバックボーンを通過する必要があるか、またはデータ リクエストがリモートのフロントエンド サーバーにより処理されるため、パフォーマンスが低下する可能性があります。

#### <a name="how-to-test"></a>テスト方法
当該支社のデバイスからツールまたは Web サイトを使用して、プロキシ サーバーが使用しているパブリック IP アドレスを判別します。たとえば、[What Is My IP Address](https://www.whatismypublicip.com/) Web ページなどを使用します。ISP により割り当てられるパブリック IP アドレスは、地理的にローカルなはずです。これは、本社のパブリック IP アドレス範囲またはクラウドベース ネットワーク セキュリティ ベンダーの IP アドレスであってはなりません。

必要に応じて、[手順 2](../networking-dns-resolution-same-location.md) がこの必須条件を満たす上で役立ちます。

<a name="crit-networking-step3"></a>
### <a name="optional-unneeded-network-hairpins-are-removed"></a>オプション: 不要なネットワーク ヘアピンの削除

ネットワーク ヘアピンの調査と、オフィス全体のパフォーマンスに与える影響の確認がなされていること。削除できるヘアピンを削除するか、サード パーティのネットワーク プロバイダーやセキュリティ プロバイダーと協力し、ネットワークに最適な Microsoft 365 ピアリングが実装されていること。

必要に応じて、[手順 3](../networking-avoid-network-hairpins.md) がこのオプション条件を満たす上で役立ちます。


<a name="crit-networking-step4"></a>
### <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a>オプション: インターネット ブラウザーとエッジ デバイスでのトラフィック バイパスの構成

最新の PAC ファイルをオンプレミスのインターネット ブラウザーに展開し、Microsoft 365 の DNS ドメイン名へのトラフィックがプロキシ サーバーをバイパスするように構成されていること。

ネットワーク境界デバイス (ファイアウォール、SSL 中断/検査、パケット検査デバイスなど) が、トラフィック バイパスを使用するか、Microsoft 365 の "最適化" および "許可" カテゴリのエンドポイントへのトラフィック処理が最小限になるように構成されていること。


#### <a name="how-to-test"></a>テスト方法

ネットワーク境界デバイスでログ ツールを使用し、Microsoft 365 を宛先とするトラフィックが検査されたり、暗号化されたり、またはその他のことで阻害されていないことを確認します。

必要に応じて、[手順 4](../networking-configure-proxies-firewalls.md) がこのオプション条件を満たす上で役立ちます。


<a name="crit-networking-step5"></a>
### <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a>オプション: クライアントと Office 365 アプリケーションが最適なパフォーマンスを実現できるように構成されている

クライアント デバイスと、Exchange Online、Skype for Business Online、SharePoint Online、Project Online の各サービスの Transmssion Control Protocol (TCP) 設定を最適化している。

必要に応じて、[手順 5](../networking-optimize-tcp-performance.md) がこのオプション条件を満たすのに役立ちます。

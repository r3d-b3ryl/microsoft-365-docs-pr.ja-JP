---
title: Microsoft 365 サービスの IPv6 サポート
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/01/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: '概要: IPv6 のサポートについて、Microsoft 365および政府機関のMicrosoft 365説明します。'
ms.openlocfilehash: 5d798f741caa1a9a2df69e1c4df1d45067d15ce3
ms.sourcegitcommit: 0251d5c6cb141055c93c83a402c3dc52c7a70dcc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2021
ms.locfileid: "61262774"
---
# <a name="ipv6-support-in-microsoft-365-services"></a>Microsoft 365 サービスの IPv6 サポート

Microsoft 365 IPv6 と IPv4 の両方をサポートしますが、IPv6 で完全にMicrosoft 365機能が完全に有効になっているわけではありません。 つまり、IPv4 と IPv6 の両方を使用してデバイスに接続するMicrosoft 365。 送信トラフィックを Microsoft 365 にフィルター処理する場合、Microsoft 365 でサポートされている IPv6 アドレスの完全な一覧は、「Microsoft 365 URL と IP アドレス範囲」の記事で[確認](urls-and-ip-address-ranges.md)できます。 ネットワークが構成され、適切な IPv6 アドレスが許可された後、Microsoft ダウンロード センターから Microsoft 365 [IPv6](https://go.microsoft.com/fwlink/?LinkId=293447)テスト プランをダウンロードできます。

> [!NOTE]
> お客様が任意の場所Microsoft 365デバイスから SaaS サービスを体験できるのが、Microsoft にとって優先事項です。 これには、IPv6 が有効なクライアントと情報システムMicrosoft 365 IPv6 からの接続と使用が可能になります。 また、政府のお客様がネットワーク上の IPv6 コミットメントを満たしながら、生産性のシナリオを中断することなく引き続きMicrosoft 365を利用できます。  
> この記事では、今日の直接 IPv6 接続Microsoft 365 SaaS サービスの一覧を示します。 直接 IPv6 接続を許可するサービスの範囲は、引き続き拡大する予定です。 Microsoft 365 (Azure Active Directory AAD) 認証サービスを含める直接 IPv6 サポートについて明示的に言及されていないサービスは、DNS64/NAT64 を IPv6 からのクライアントと環境からのみ接続する必要があると見なす必要があります。  これは、NIST Special [Publication 500-267A Revision 1](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.500-267Ar1.pdf) NAT64/DNS64 の既存の NIST USGv6 ドキュメントで現在説明されている「移行メカニズムの機能要件」に記載されている意図に合わせ、採用できるテクノロジです。
> - NAT64 による移行メカニズム [NAT64 RFC6146](https://datatracker.ietf.org/doc/html/rfc6146) ステートフル NAT64 のサポート: IPv6 クライアントから IPv4 サーバーへのネットワーク アドレスとプロトコル変換
> - 移行メカニズム DNS64 の DNS64 のサポート。 [RFC6147](https://datatracker.ietf.org/doc/html/rfc6147) DNS64: IPv6 クライアントから IPv4 Server へのネットワーク アドレス変換の DNS 拡張機能

  
## <a name="ipv6-support-in-microsoft-365-subscription-service"></a>サブスクリプション サービスでの IPv6 Microsoft 365サポート

### <a name="exchange-online-and-ipv6"></a>Exchange Online IPv6

IPv6 への接続に使用するプログラムExchange Online IPv6 がサポートされている場合、有線ネットワークとワイヤレス ネットワークの両方で既定で IPv6 が使用されます。 ネットワークへの通信を制御する場合Exchange Online URL と IP アドレス範囲の IP Microsoft 365[を使用します](urls-and-ip-address-ranges.md)。
  
### <a name="sharepoint-online-and-ipv6"></a>SharePointおよび IPv6

 **Microsoft 365 G1/G3/G4/K1** SharePoint Online への接続に使用するプログラムが IPv6 をサポートしている場合、IPv6 は既定で使用されます。
  
 **パブリック マルチテナント クラウド** Microsoft は、SharePointオンライン IPv6 を有効にしています。 組織の DNS インフラストラクチャに CIDR の指定された IP アドレスを指定する必要があります。 IPv6 をテナントで有効にするために、この DNS インフラストラクチャを他の組織と共有することはできません。 IPv6 が有効になると、オンラインに接続するために使用するプログラムSharePoint IPv6 がサポートされている場合は、既定で IPv6 が使用されます。
  
オンラインへの接続に使用するプログラムSharePoint IPv6 がサポートされている場合、有線ネットワークとワイヤレス ネットワークの両方で既定で IPv6 が使用されます。 オンラインへの通信を制御する場合SharePoint URL と IP アドレス範囲の IP [Microsoft 365を使用します](urls-and-ip-address-ranges.md)。
  
 
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business IPv6

IPv6 はサポートされていないのでSkype for Business有効にすることはできません。

### <a name="microsoft-teams-sip-gateway-and-ipv6"></a>Microsoft Teams SIP ゲートウェイ、IPV6

Microsoft Teamsおよび SIP ゲートウェイは IPv4 のみをサポートします。 サービスMicrosoft Teamsクライアントは、IPv4 と IPv6 の両方をサポートします。 ネットワークへの通信を制御する場合Microsoft Teams URL と IP アドレス範囲の IP [Microsoft 365を使用します](urls-and-ip-address-ranges.md)。
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection IPv6

Exchange Online Protection (EOP) は、トランスポート層セキュリティ プロトコルを使用して送信が行われる場合に IPv6 をサポートします。 EOP 範囲の場合は、URL [Microsoft 365 IP アドレス範囲を使用します](urls-and-ip-address-ranges.md)。
  
### <a name="ipv6-support-for-microsoft-365-government-offerings"></a>IPv6 による政府機関向けMicrosoft 365サポート

Microsoft 365の IPv6 サポートは、Office の管理および予算 (OMB) メモに準拠しています。また、連邦政府によるインターネット プロトコル バージョン 6 (IPv6) の導入覚書にも準拠しています。 [Microsoft Microsoft 365は](https://go.microsoft.com/fwlink/p/?LinkId=325414)、分離されたコミュニティ クラウドに米国政府のデータを格納するマルチテナント サービスです。 他のMicrosoft 365と同様に、Exchange Online、Skype for Business、SharePoint Online、および Microsoft 365 Apps for enterprise を含むコラボレーション サービスを提供Microsoft 365 Apps for enterprise。 

Microsoft Microsoft 365サービスは、2013 以降にのみ適用されます。 政府機関向けサービスのMicrosoft 365詳細については[、「Annouing Microsoft 365: A US](https://go.microsoft.com/fwlink/p/?LinkId=325414)Government Community Cloud」 を参照してください。 国際武器規制 (ITAR) は、米国軍需リスト [(USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415)の防衛関連の記事やサービスの輸出入を制御する米国政府の規制のセットです。 

Microsoft Microsoft 365 for Enterprises は、ITAR の対象となる連邦情報セキュリティ管理 (FISMA) 認定および商用エンティティを必要とする米国連邦政府機関のセキュリティ、プライバシー、および規制コンプライアンス要件をサポートする Microsoft 生産性向上ソリューション向け専用のホスティング サービスを提供します。
  
## <a name="things-to-consider-when-using-ipv6-and-microsoft-365"></a>IPv6 と IPv6 を使用する場合のMicrosoft 365

IPv6 を無効にすることをお勧めします。 詳細については、このガイダンス記事 [を参照してください](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)。 ネットワークで使用されている IP バージョンを確認するには、次の点を検討してください。
  
- コマンド プロンプトでの **IPConfig** コマンドの表示に"IPv6 Address" または "Temporary IPv6 Address" という名前の行が含まれている場合は、環境に IPv6 があります。

- すべての IPv6 アドレスが "fe80" で始まり、"Link-Local IPv6 Address" という名前の行に対応する場合は、環境に IPv6 が含まれます。

これらの考慮事項は、ネットワークに適用される場合があります。
  
- パブリック サブスクリプション サービスでは、IPv6 を使用したクレジット カードによる購入はサポートされていません。 これは、政府が (EA) Government Community Cloud (GCC) ライセンスEnterprise Agreement適用されません。

- IPv6 は、一部の Rights Management Services (RMS) シナリオをサポートしません。

- IPv6 は IPv6 をサポート® Enterprise BlackBerry サーバー (BES) をサポートしません。

- Active Directory フェデレーション サービス (AD FS) を Microsoft 365 で使用する場合、IPv6 を使用して AD FS ネットワーク エンドポイントを Microsoft 365 に宣伝することはできません。 これらのレコードを使用する場合は、FS DNS ADに AAAA レコードを含Exchange Online。 

ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/o365ip6]()

## <a name="see-also"></a>関連項目

[IPv6 ラーニングロードマップ](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 サバイバル ガイド](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)

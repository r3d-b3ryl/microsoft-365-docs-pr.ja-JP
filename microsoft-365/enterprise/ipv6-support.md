---
title: Office 365 サービスでの IPv6 サポート
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: '概要: IPv6 のサポートについて、Microsoft Office 365および政府機関のOffice 365説明します。'
ms.openlocfilehash: d526cc2c701ebfcfd322c10c3147f085c6eecb8acb47ed6a55a3c95641ea76cb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53859001"
---
# <a name="ipv6-support-in-office-365-services"></a>Office 365 サービスでの IPv6 サポート

*この記事は、Microsoft 365 Enterprise と Office 365 Enterprise の両方に適用されます。*

Office 365 IPv6 と IPv4 の両方をサポートしています。ただし、IPv6 でOffice 365機能が完全に有効になっているわけではありません。 つまり、IPv4 と IPv6 の両方を使用してデバイスに接続するOffice 365。 送信トラフィックを Office 365 にフィルター処理する場合、Office 365 でサポートされている IPv6 アドレスの完全な一覧は[、「Office 365 URL](urls-and-ip-address-ranges.md)と IP アドレス範囲」の記事で確認できます。 ネットワークが構成され、適切な IPv6 アドレスが許可された後、Microsoft ダウンロード センターから Office 365 [IPv6](https://go.microsoft.com/fwlink/?LinkId=293447)テスト プランをダウンロードできます。
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>サブスクリプション サービスでの IPv6 Office 365サポート

### <a name="exchange-online-and-ipv6"></a>Exchange Online IPv6

IPv6 への接続に使用するプログラムExchange Online IPv6 がサポートされている場合、有線ネットワークとワイヤレス ネットワークの両方で既定で IPv6 が使用されます。 ネットワークへの通信を制御する場合Exchange Online URL と IP アドレス範囲の IP Office 365[を使用します](urls-and-ip-address-ranges.md)。
  
### <a name="sharepoint-online-and-ipv6"></a>SharePointオンラインと IPv6

 **Office 365 Government G1/G3/G4/K1** オンラインへの接続に使用するプログラムSharePoint IPv6 がサポートされている場合は、既定で IPv6 の使用が試行されます。
  
 **パブリック マルチテナント クラウド** Microsoft は、SharePointオンライン IPv6 を有効にしています。 組織の DNS インフラストラクチャに CIDR の指定された IP アドレスを指定する必要があります。 IPv6 をテナントで有効にするために、この DNS インフラストラクチャを他の組織と共有することはできません。 IPv6 が有効になると、オンラインに接続するために使用するプログラムSharePoint IPv6 がサポートされている場合は、既定で IPv6 が使用されます。
  
オンラインへの接続に使用するプログラムSharePoint IPv6 がサポートされている場合、有線ネットワークとワイヤレス ネットワークの両方で既定で IPv6 が使用されます。 オンラインへの通信を制御する場合SharePoint URL と IP アドレス範囲の IP [Office 365を使用します](urls-and-ip-address-ranges.md)。
  
 
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business IPv6

IPv6 はサポートされていないのでSkype for Business有効にすることはできません。

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams IPV6

Microsoft Teamsダイレクト ルーティングは IPv4 のみをサポートします。 サービスMicrosoft Teamsクライアントは、IPv4 と IPv6 の両方をサポートします。 サーバーへの通信を制御する場合Microsoft Teams URL と IP アドレス範囲の IP [Office 365を使用します](urls-and-ip-address-ranges.md)。
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection IPv6

Exchange Online Protection (EOP) は、トランスポート層セキュリティ プロトコルを使用して送信が行われる場合に IPv6 をサポートします。 EOP 範囲の場合は、URL [Office 365 IP アドレス範囲を使用します](urls-and-ip-address-ranges.md)。
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>政府機関向け製品の IPv6 Office 365サポート

Office 365政府機関向け IPv6 サポートは、Office の経営部門および機関の最高情報責任者のための管理予算 (OMB) メモ、およびインターネット プロトコル バージョン 6 (IPv6) の連邦政府導入覚書に準拠しています。 [Microsoft Office 365は](https://go.microsoft.com/fwlink/p/?LinkId=325414)、分離されたコミュニティ クラウドに米国政府のデータを格納するマルチテナント サービスです。 他のOffice 365製品と同様に、Exchange Online、Skype for Business、SharePoint Online、およびMicrosoft 365 Apps for enterprise。 

政府機関Microsoft Office 365は、2013 以降にのみ適用されます。 政府機関向けサービスのOffice 365詳細については[、「Annouing Office 365: A US](https://go.microsoft.com/fwlink/p/?LinkId=325414)Government Community Cloud」 を参照してください。 国際武器規制 (ITAR) は、米国軍需リスト [(USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415)の防衛関連の記事やサービスの輸出入を制御する米国政府の規制のセットです。 

Microsoft Office 365 for Enterprises は、ITAR の対象となる連邦情報セキュリティ管理 (FISMA) 認定および商用エンティティを必要とする米国連邦政府機関のセキュリティ、プライバシー、および規制コンプライアンス要件をサポートする Microsoft 生産性ソリューション向け専用のホスティング サービスを提供します。
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>IPv6 と IPv6 を使用する場合のOffice 365

IPv6 を無効にすることをお勧めします。 詳細については、このガイダンス記事 [を参照してください](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)。 ネットワークで使用されている IP バージョンを確認するには、次の点を検討してください。
  
- コマンド プロンプトでの **IPConfig** コマンドの表示に"IPv6 Address" または "Temporary IPv6 Address" という名前の行が含まれている場合は、環境に IPv6 があります。

- すべての IPv6 アドレスが "fe80" で始まり、"Link-Local IPv6 Address" という名前の行に対応する場合は、環境に IPv6 が含まれます。

これらの考慮事項は、ネットワークに適用される場合があります。
  
- パブリック サブスクリプション サービスでは、IPv6 を使用したクレジット カードによる購入はサポートされていません。 これは、政府が (EA) Government Community Cloud (GCC) ライセンスEnterprise Agreement適用されません。

- IPv6 は、一部の Rights Management Services (RMS) シナリオをサポートしません。

- IPv6 は IPv6 をサポート® Enterprise BlackBerry サーバー (BES) をサポートしません。

- Active Directory フェデレーション サービス (AD FS) を Office 365 で使用する場合、IPv6 を使用して AD FS ネットワーク エンドポイントを Office 365 に宣伝することはできません。 これらのレコードを使用する場合は、FS DNS ADに AAAA レコードを含Exchange Online。 

ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>関連項目

[IPv6 ラーニングロードマップ](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 サバイバル ガイド](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)

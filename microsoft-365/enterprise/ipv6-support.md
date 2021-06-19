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
description: '概要: 365 コンポーネントと 365 Microsoft Office 365 の政府機関製品での IPv6 サポートOffice説明します。'
ms.openlocfilehash: a509b19711092bddf153a677c41860e7a4e5277a
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028909"
---
# <a name="ipv6-support-in-office-365-services"></a>Office 365 サービスでの IPv6 サポート

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Office 365 は IPv6 と IPv4 の両方をサポートしています。ただし、IPv6 で 365 Office機能が完全に有効になっているわけではありません。 つまり、IPv4 と IPv6 の両方を使用して 365 に接続Officeです。 送信トラフィックを Office 365 にフィルター処理する場合、Office 365 でサポートされている IPv6 アドレスの完全な一覧は、記事 [Office 365 URL](urls-and-ip-address-ranges.md)と IP アドレス範囲に記載されています。 ネットワークが構成され、適切な IPv6 アドレスが許可された後、microsoft ダウンロード センターから [Office 365 IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) テスト プランをダウンロードできます。
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>IPv6 のサポート (Office 365 サブスクリプション サービス)

### <a name="exchange-online-and-ipv6"></a>Exchange Online と IPv6

Exchange Online への接続に使用するプログラムが IPv6 をサポートしている場合は、有線ネットワークとワイヤレス ネットワークの両方で既定で IPv6 が使用されます。 Exchange Online への通信を制御する場合は、365 の URL と IP アドレス範囲Office IP [アドレス範囲を使用します](urls-and-ip-address-ranges.md)。
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online と IPv6

 **Office 365 Government G1/G3/G4/K1** SharePoint Online への接続に使用するプログラムが IPv6 をサポートしている場合は、既定で IPv6 の使用が試行されます。
  
 **パブリック マルチテナント クラウド** Microsoft は、要求に応じて SharePoint Online IPv6 を有効にしています。 組織の DNS インフラストラクチャに CIDR の指定された IP アドレスを指定する必要があります。 IPv6 をテナントで有効にするために、この DNS インフラストラクチャを他の組織と共有することはできません。 IPv6 を有効にした後、SharePoint Online への接続に使用するプログラムが IPv6 をサポートしている場合、IPv6 は既定で IPv6 を使用します。
  
SharePoint Online への接続に使用するプログラムが IPv6 をサポートしている場合、有線ネットワークとワイヤレス ネットワークの両方で IPv6 が既定で使用されます。 SharePoint Online への通信を制御する場合は [、365](urls-and-ip-address-ranges.md)の URL と IP アドレス範囲Office IP アドレス範囲を使用します。
  
 
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business および IPv6

IPv6 は Skype for Business ではサポートされていないので、有効にできなくなりました。

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams と IPV6

Microsoft Teams ダイレクト ルーティングは IPv4 のみをサポートします。 Microsoft Teams サービスとクライアントは、IPv4 と IPv6 の両方をサポートしています。 Microsoft Teams への通信を制御する場合は [、365](urls-and-ip-address-ranges.md)の URL と IP アドレス範囲Office IP アドレス範囲を使用します。
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection と IPv6

Exchange Online Protection (EOP) は、トランスポート層セキュリティ プロトコルを使用して送信が行われる場合、IPv6 をサポートします。 EOP 範囲の場合は [、365 Office IP アドレス範囲を使用します](urls-and-ip-address-ranges.md)。
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>365 の政府機関向Office IPv6 サポート

Office 365 IPv6 による政府機関向けサポートは、Office の経営部門および機関の最高情報責任者のための管理予算 (OMB) メモ、およびインターネット プロトコル バージョン 6 (IPv6) の連邦政府導入覚書に準拠しています。 [Microsoft Office 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) は、分離されたコミュニティ クラウドに米国政府のデータを格納するマルチテナント サービスです。 他の Office 365 製品と同様に、Exchange Online、Skype for Business、SharePoint Online、Microsoft 365 Apps for enterprise などの生産性とコラボレーション サービスを提供します。 

365 Microsoft Officeは、2013 以降にのみ適用されます。 365 政府機関向Office詳細については [、「Annouing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414)」を参照してください。 国際武器規制 (ITAR) は、米国軍需リスト [(USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415)の防衛関連の記事やサービスの輸出入を制御する米国政府の規制のセットです。 

Microsoft Office 365 for Enterprises は、ITAR の対象となる連邦情報セキュリティ管理 (FISMA) 認定および商用エンティティを必要とする米国連邦政府機関のセキュリティ、プライバシー、および規制コンプライアンス要件をサポートする Microsoft 生産性向上ソリューション向け専用のホスティング サービスを提供します。
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>IPv6 および 365 を使用する場合Office検討する

IPv6 を無効にすることをお勧めします。 詳細については、このガイダンス記事 [を参照してください](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)。 ネットワークで使用されている IP バージョンを確認するには、次の点を検討してください。
  
- コマンド プロンプトでの **IPConfig** コマンドの表示に"IPv6 Address" または "Temporary IPv6 Address" という名前の行が含まれている場合は、環境に IPv6 があります。

- すべての IPv6 アドレスが "fe80" で始まり、"Link-Local IPv6 Address" という名前の行に対応する場合は、環境に IPv6 が含まれます。

これらの考慮事項は、ネットワークに適用される場合があります。
  
- パブリック サブスクリプション サービスでは、IPv6 を使用したクレジット カードによる購入はサポートされていません。 これは、政府機関が EA (EA) ライセンスを使用マイクロソフトエンタープライズ契約コミュニティ クラウド (GCC) には適用されません。

- IPv6 は、一部の Rights Management Services (RMS) シナリオをサポートしません。

- IPv6 は IPv6 をサポート®ため、BlackBerry エンタープライズ サーバー (BES) はサポートされません。

- Active Directory フェデレーション サービス (AD FS) を Office 365 で使用する場合、IPv6 を使用して AD FS ネットワーク エンドポイントを Office 365 に広告はサポートされません。 Exchange Online を使用する場合は、FS DNS AD AAAA レコードを含める必要があります。 

ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>関連項目

[IPv6 ラーニング ロードマップ](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 サバイバル ガイド](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)

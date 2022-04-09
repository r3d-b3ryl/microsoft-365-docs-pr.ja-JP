---
title: Microsoft 365 サービスの IPv6 サポート
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/03/2021
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
description: '概要: Microsoft 365 コンポーネントと Microsoft 365 政府機関向けサービスでの IPv6 サポートについて説明します。'
ms.openlocfilehash: a6a2e11ff2e312c02f10d152fe580bdead5fa7c9
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301956"
---
# <a name="ipv6-support-in-microsoft-365-services"></a>Microsoft 365 サービスの IPv6 サポート

Microsoft 365 では、IPv6 と IPv4 の両方がサポートされます。ただし、すべての Microsoft 365 機能が IPv6 で完全に有効になっているわけではありません。 つまり、Microsoft 365 に接続するには IPv4 と IPv6 の両方を使用する必要があります。 Microsoft 365 への送信トラフィックをフィルター処理する場合、Microsoft 365 でサポートされている IPv6 アドレスの完全なリストは、「[Microsoft 365 URL と IP アドレス範囲](urls-and-ip-address-ranges.md)」 の記事で確認できます。 ネットワークを構成し、適切な IPv6 アドレスを許可すると、Microsoft ダウンロード センターから [Microsoft 365 IPv6 テスト プラン](https://go.microsoft.com/fwlink/?LinkId=293447) をダウンロードできるようになります。

> [!NOTE]
> Microsoft 365 の SaaS サービスを、場所やデバイスを問わずに体験できるようにすることは、Microsoft の優先事項です。 これには、お客様が IPv6 対応および IPv6 のみのクライアントと情報システムから Microsoft 365 に接続して使用できるようにすることが含まれます。 また、政府機関のお客様がネットワーク上で IPv6 コミットメントを満たしながら、中断することなくMicrosoft 365 の生産性シナリオを引き続き使用できるようにすることも含まれます。  
> この記事では、現在 IPv6 への直接接続を許可する Microsoft 365 SaaS サービスのリストを示します。 IPv6 への直接接続を許可するサービスの範囲は、引き続き拡張される予定です。 直接 IPv6 のサポートについて明示的に言及されていないMicrosoft 365 サービスには、Azure Active Directory (AAD) 認証サービスを含めるには、DNS64/NAT64 を IPv6 のみのクライアントと環境から接続する必要があると見なす必要があります。  これは、現在、既存の NIST USGv6 ドキュメントで概説されている意図に沿っています。[NIST Special Publication 500-267A Revision 1](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.500-267Ar1.pdf) NAT64/DNS64 の移行メカニズム機能要件は、採用できるテクノロジです。
> - NAT64 の移行メカニズム NAT64 のサポート [RFC6146](https://datatracker.ietf.org/doc/html/rfc6146) ステートフル NAT64: IPv6 クライアントから IPv4 サーバーへのネットワーク アドレスとプロトコル変換
> - 移行メカニズム DNS64 の DNS64 サポート。 [RFC6147](https://datatracker.ietf.org/doc/html/rfc6147) DNS64: IPv6 クライアントから IPv4 サーバーへのネットワーク アドレス変換の DNS 拡張機能

  
## <a name="ipv6-support-in-microsoft-365-subscription-service"></a>Microsoft 365 サブスクリプション サービスでの IPv6 のサポート

### <a name="exchange-online-and-ipv6"></a>Exchange Online と IPv6

Exchange Online への接続に使用するプログラムが IPv6 をサポートしている場合は、有線および無線のどちらのネットワークでも既定で IPv6 が使用されます。 Exchange Online への通信を制御する場合は、[Microsoft 365 URL と IP アドレス範囲](urls-and-ip-address-ranges.md) の IP アドレス範囲を使用します。
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online と IPv6

 **Office 365 Government G1/G3/G4/K1** SharePoint Online への接続に使用するプログラムが IPv6 をサポートする場合、既定で IPv6 の使用を試みます。
  
 **パブリック マルチテナント クラウド** ユーザーの要求に応じて Microsoft が SharePoint Online IPv6 を有効にします。 組織の DNS インフラストラクチャの CIDR に示された IP アドレスを指定する必要があります。 テナントで IPv6 を有効にするために、この DNS インフラストラクチャを他の組織で共有できないことに注意してください。 IPv6 が有効になった後、SharePoint Online への接続に使用するプログラムが IPv6 をサポートしている場合、既定で IPv6 が使用されます。
  
SharePoint Online への接続に使用するプログラムが IPv6 をサポートしている場合、有線および無線のどちらのネットワークでも既定で IPv6 が使用されます。 SharePoint Online への通信を制御する場合は、[Microsoft 365 URL と IP アドレス範囲](urls-and-ip-address-ranges.md) の IP アドレス範囲を使用します。
  
 
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business および IPv6

IPv6 は Skype for Business ではサポートされておらず、有効化することはできませんのでご注意ください。

### <a name="microsoft-teams-sip-gateway-and-ipv6"></a>Microsoft Teams、SIP ゲートウェイ、および IPV6

Microsoft Teams ダイレクト ルーティングと SIP ゲートウェイでは、IPv4 のみがサポートされます。 Microsoft Teams サービスとクライアントは、IPv4 と IPv6 の両方をサポートしています。 Microsoft Teams への通信を制御する場合は、[Microsoft 365 URL と IP アドレス範囲の IP アドレス範囲](urls-and-ip-address-ranges.md) を使用します。
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection と IPv6

トランスポート層セキュリティ プロトコルを介して転送が行われる場合、Exchange Online Protection (EOP) は IPv6 をサポートします。 EOP 範囲の場合は、[Microsoft 365 URL と IP アドレス範囲](urls-and-ip-address-ranges.md) を使用します。
  
### <a name="ipv6-support-for-microsoft-365-government-offerings"></a>Microsoft 365 政府機関向けサービスの IPv6 サポート

政府機関が提供する Microsoft 365 の IPv6 サポートは、行政管理予算局 (OMB) の 「行政機関の最高情報責任者のための覚書」、および 「連邦政府によるインターネットプロトコル バージョン6 (IPv6) の採用に関する覚書」 に準拠しています。 [Microsoft Microsoft 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) は、分離されたコミュニティ クラウドに米国政府データを格納するマルチテナント サービスです。 他の Office 365 製品と同様に、Exchange Online、Skype for Business、SharePoint Online、Microsoft 365 Apps for enterprise など、生産性の向上とコラボレーション サービスを提供します。 

Microsoft の Microsoft Office 365 Government 製品は、2013 以降のみに適用されます。 Microsoft 365 政府機関向けサービスの詳細については、「[Microsoft 365 for Government を発表: 米国政府のコミュニティ・クラウド](https://go.microsoft.com/fwlink/p/?LinkId=325414)」 を参照してください。 国際武器取引に関する規則 (ITAR) は、[合衆国武器リスト (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415) に列記された国防関連の物品およびサービスの輸出入を規制する合衆国連邦政府の規則です。 

Microsoft Office 365 for Enterprises は、Microsoft 生産性向上ソリューションのための専用のホスティング サービスを提供し、これらは情報セキュリティ マネジメント法 (FISMA) の認定や商用エンティティの ITAR 準拠を要求する連邦政府機関のセキュリティ、プライバシー、規制順守の要件に対応しています。
  
## <a name="things-to-consider-when-using-ipv6-and-microsoft-365"></a>IPv6 および Microsoft 365 の使用に関する考慮事項

IPv6 を無効にすることはお勧めしません。 詳細については、この 「[ガイダンスの記事](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)」 を参照してください。 使用するネットワーク上の IP のバージョンを確認するには、以下の事項を検討してください。
  
- コマンド プロンプトで **IPConfig** コマンドを実行し、「IPv6 Address (IPv6 アドレス)」または「Temporary IPv6 Address (一時 IPv6 アドレス)」という行が表示された場合、その環境では IPv6 を使用できます。

- すべての IPv6 アドレスが 「fe80」 で始まり、「Link-Local IPv6 Address (リンクローカル IPv6 アドレス)」 という行に対応している場合、それは IPv6 環境ではありません。

以下の事項がネットワークに適用される場合があります。
  
- パブリック サブスクリプション サービスでは、IPv6 を介したクレジット カードでの購入はサポートされません。 ただし、政府機関コミュニティ クラウド (GCC) の場合、政府機関には Enterprise Agreement (EA) ライセンスがあるため、これは適用されません。

- IPv6 では、Rights Management サービス (RMS) の一部のシナリオはサポートされません。

- BlackBerry では IPv6 がサポートされていないため、IPv6 は BlackBerry® Enterprise Server (BES) で使用できません。

- Microsoft 365 で Active Directory フェデレーション サービス (AD FS) (AD FS) を使用する場合、IPv6 を使用して Microsoft 365にAD FS ネットワーク エンドポイントを広告することはサポートされていません。 Exchange Online を使用する場合は、AD FS DNS エントリに AAAA レコードを含めないようにしてください。 

ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/o365ip6]()

## <a name="see-also"></a>関連項目

[IPv6 Learning Roadmap](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 の生存ガイド](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)

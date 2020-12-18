---
title: Microsoft 365 での暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365solution-mip
- m365initiative-compliance
description: Office 365 では、利用可能な最も強力な暗号化、プロトコル、テクノロジを使用して、保存中および転送中にコンテンツが暗号化されます。 Office 365 での暗号化の概要について説明します。
ms.openlocfilehash: 1aee9d401891e807f572c1eed2bc22a54f39e534
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709570"
---
# <a name="encryption"></a>暗号化

暗号化は、ファイル保護と情報保護戦略の重要な部分です。 この記事では、365 年 365 日の暗号化Office説明します。 組織の暗号化を設定する方法や、組織のドキュメントをパスワードで保護する方法など、暗号化タスクOfficeします。
  
- TLS などの証明書とテクノロジの詳細については、Office 365 での暗号化に関するテクニカル [リファレンスの詳細を](technical-reference-details-about-encryption.md)参照してください。

- 組織の暗号化を構成または設定する方法については、「Office [365 Enterprise](set-up-encryption.md)での暗号化の設定」を参照してください。

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>暗号化とは何ですか。また、Office 365 でどのように機能しますか。

暗号化プロセスは、データ (プレーンテキストと呼ばれる) を暗号テキストにエンコードします。 プレーンテキストとは異なり、暗号テキストは暗号化が解除されていない限り、ユーザーやコンピューターでは使用できません。 復号化には、承認されたユーザーのみが持つ暗号化キーが必要です。 暗号化を使用すると、承認された受信者のみがコンテンツの暗号化を解除できます。 コンテンツには、ファイル、電子メール メッセージ、予定表のエントリが含まれます。
  
それ自体による暗号化によって、コンテンツが傍受されるのを防ぐ必要はありません。 暗号化は、組織のより大きな情報保護戦略の一部です。 暗号化を使用すると、承認された関係者のみが暗号化されたデータを使用できます。
  
暗号化の複数のレイヤーを同時に設定できます。 たとえば、電子メール メッセージと、電子メールが流れる通信チャネルを暗号化できます。 Office 365 では、データは保存中および転送中に、いくつかの強力な暗号化プロトコル、およびトランスポート層セキュリティ/Secure Sockets Layer (TLS/SSL)、インターネット プロトコル セキュリティ (IPSec)、および Advanced Encryption Standard (AES) を含むテクノロジを使用して暗号化されます。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>保存中のデータと転送中のデータの暗号化

 保存データの例としては、SharePoint ライブラリにアップロードしたファイル、Project Online データ、Skype for Business 会議にアップロードしたドキュメント、メールボックス内のフォルダーに保存した電子メール メッセージと添付ファイル、OneDrive for Business にアップロードしたファイルが含まれます。
  
 **送信中のデータの** 例としては、配信中のメール メッセージや、オンライン会議で行っている会話があります。 Office 365 では、ユーザーのデバイスが Microsoft サーバーと通信している場合、または Microsoft サーバーが別のサーバーと通信している場合は常に、データが送信中です。
  
365 Officeでは、複数のレイヤーと種類の暗号化が組み合わせてデータを保護します。 次の表に、追加情報へのリンクを含む例を示します。
  
|**コンテンツの種類**|**暗号化テクノロジ**|**追加情報**|
|:-----|:-----|:-----|
|デバイス上のファイル。 これらのファイルには、フォルダーに保存された電子メール メッセージ、Office、タブレット、または電話に保存されたドキュメント、または Microsoft クラウドに保存されたデータが含まれます。  <br/> |Microsoft データセンターの BitLocker。 BitLocker は、Windows コンピューターやタブレットなどのクライアント コンピューターでも使用できます。  <br/> Microsoft データセンターでの分散キー マネージャー (DKM)  <br/> Microsoft 365 のカスタマー キー  <br/> |[Windows IT センター: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft セキュリティ センター: 暗号化](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [クラウド セキュリティ制御シリーズ: 保存データの暗号化](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online がメールの機密情報をセキュリティで保護する方法](exchange-online-secures-email-secrets.md) <br/> [カスタマー キーによるサービスの暗号化](customer-key-overview.md) <br/> |
|ユーザー間で転送中のファイル。 これらのファイルには、ユーザー Office共有されているドキュメントや SharePoint リスト アイテムを含めることもできます。  <br/> |転送中のファイルの TLS  <br/> |[OneDrive for Business および SharePoint Online におけるデータ暗号化](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business Online: セキュリティとアーカイブ](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|受信者間で転送中のメール。 この電子メールには、Exchange Online によってホストされる電子メールが含まれます。  <br/> |Officeメールの Azure Rights Management、S/MIME、TLS による 365 Message Encryption の使用  <br/> |[Office 365 Message Encryption (OME)](ome.md) <br/> [Office 365 での電子メールの暗号化](email-encryption.md) <br/> [Exchange Online が TLS を使って Office 365 のメール接続をセキュリティで保護する方法](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Microsoft Teams を使用して受信者間で転送中のチャット、メッセージ、およびファイル。 <br/> |Teams では、インスタント メッセージの暗号化に TLS と MTLS を使用します。 メディア トラフィックは Secure RTP (SRTP) を使用して暗号化されます。 Teams は、暗号化キー交換に FIPS (Federal Information Processing Standard) 準拠アルゴリズムを使用します。 <br/> |[Teams の暗号化](https://docs.microsoft.com/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>セキュリティとコンプライアンスの要件を満たすために暗号化を詳細に制御する必要がある場合は、

Microsoft 365 は、Microsoft が管理するボリューム暗号化、ファイルの暗号化、およびメールボックスの暗号化に関するソリューションを、Office 365 で提供しています。 さらに、Microsoft では、管理および制御できる暗号化ソリューションを提供しています。 これらの暗号化ソリューションは Azure 上に構築されています。
  
詳細については、次のリソースを参照してください。
  
- [Azure Active Directory Rights Management の概要](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [管理センターで Rights Management をアクティブ化する](https://docs.microsoft.com/microsoft-365/enterprise/activate-rms-in-microsoft-365)

- [SharePoint 管理センターで Information Rights Management (IRM) を設定する](set-up-irm-in-sp-admin-center.md)

- [Office 365 のカスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [Microsoft 365 の二重キー暗号化](double-key-encryption.md)

## <a name="how-do-i"></a>方法

|**このタスクを実行するには**|**次のリソースを参照してください。**|
|:-----|:-----|
|組織の暗号化を設定する  <br/> |[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md) <br/> |
|証明書、テクノロジ、TLS 暗号スイートの詳細を表示する <br/> |[暗号化に関する技術的な詳細](technical-reference-details-about-encryption.md) <br/> |
|モバイル デバイスで暗号化されたメッセージを処理する  <br/> |[暗号化されたメッセージを Android デバイスで表示する](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [iPhone または iPad で暗号化されたメッセージを表示する](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|パスワード保護を使用してドキュメントを暗号化する  <br/><br/>  パスワード保護は、ブラウザーではサポートされていません。 パスワード保護には、デスクトップ バージョンの Word、Excel、PowerPoint を使用します。 |[ドキュメント、ブック、またはプレゼンテーションの保護を追加または削除する](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Choose an **Add protection section,** and then see **Encrypt with Password**.  |
|ドキュメントから暗号化を削除する  <br/> |[ドキュメント、ブック、またはプレゼンテーションの保護を追加または削除する](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Choose a **Remove protection** section, and then see Remove **password encryption**.  |


## <a name="related-topics"></a>関連項目

[Microsoft 365 のセキュリティおよび情報保護機能を計画する](plan-for-security-and-compliance.md)

[ビジネス 向け Microsoft 365 プランをセキュリティで保護する上位 10 の方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)

[Microsoft Stream ビデオ レベルの暗号化と再生フロー](https://docs.microsoft.com/stream/network-overview#video-level-encryption-and-playback-flow)

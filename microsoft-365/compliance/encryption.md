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
description: 365 Officeを使用すると、コンテンツは、利用可能な最も強力な暗号化、プロトコル、およびテクノロジを使用して、保存時および転送中に暗号化されます。 365 で暗号化の概要をOfficeします。
ms.openlocfilehash: c54508434c5ae5126a79eba1cb6dab3851d8f746
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926445"
---
# <a name="encryption"></a>暗号化

暗号化は、ファイル保護と情報保護戦略の重要な部分です。 この記事では、365 の暗号化のOfficeします。 組織の暗号化を設定する方法や、ドキュメントをパスワードで保護する方法など、暗号化タスクOfficeしてください。
  
- TLS などの証明書とテクノロジの詳細については [、「365](technical-reference-details-about-encryption.md)での暗号化に関するテクニカル リファレンスOffice参照してください。

- 組織の暗号化を構成または設定する方法の詳細については、「Set up encryption [in Office 365 Enterprise 」を参照してください](set-up-encryption.md)。

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>暗号化とは何か、365 でどのように機能するかOffice。

暗号化プロセスは、データ (プレーン テキストと呼ばれます) を暗号テキストにエンコードします。 プレーン テキストとは異なり、暗号テキストが暗号化解除されるまでは、暗号化テキストをユーザーまたはコンピューターで使用できません。 復号化には、承認されたユーザーのみが持つ暗号化キーが必要です。 暗号化を使用すると、承認された受信者のみがコンテンツを解読できます。 コンテンツには、ファイル、電子メール メッセージ、予定表エントリなどがあります。
  
暗号化自体では、コンテンツの傍受は防止しません。 暗号化は、組織のより大きな情報保護戦略の一部です。 暗号化を使用すると、承認された関係者のみが暗号化されたデータを使用できます。
  
複数の暗号化レイヤーを同時に設定できます。 たとえば、電子メール メッセージと、電子メールが流れる通信チャネルも暗号化できます。 Office 365 では、データは、いくつかの強力な暗号化プロトコルと、トランスポート層セキュリティ/Secure Sockets Layer (TLS/SSL)、インターネット プロトコル セキュリティ (IPSec)、および高度暗号化標準 (AES) を含むテクノロジを使用して、保存時および転送中に暗号化されます。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>保存中のデータと転送中のデータの暗号化

 保存中のデータの例には、SharePoint ライブラリにアップロードしたファイル、Project Online データ、Skype for Business 会議にアップロードしたドキュメント、メールボックス内のフォルダーに保存した電子メール メッセージと添付ファイル、OneDrive for Business にアップロードしたファイルが含まれます。
  
 **転送中のデータの例** としては、配信中のメール メッセージや、オンライン会議で行う会話があります。 365 Officeでは、ユーザーのデバイスが Microsoft サーバーと通信している場合、または Microsoft サーバーが別のサーバーと通信している場合は常に、データが転送中です。
  
365 Officeでは、複数のレイヤーと種類の暗号化が一緒に機能し、データを保護します。 次の表に、追加情報へのリンクを含むいくつかの例を示します。
  
|**コンテンツの種類**|**暗号化テクノロジ**|**追加情報**|
|:-----|:-----|:-----|
|デバイス上のファイル。 これらのファイルには、フォルダーに保存された電子メール メッセージ、Officeタブレット、または電話に保存されたドキュメント、または Microsoft クラウドに保存されたデータが含まれます。  <br/> |Microsoft データセンターの BitLocker。 BitLocker は、Windows コンピューターやタブレットなどのクライアント コンピューターでも使用できます。  <br/> Microsoft データセンターの分散キー マネージャー (DKM)  <br/> Microsoft 365 のカスタマー キー  <br/> |[Windows IT センター: BitLocker](/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft Trust Center: 暗号化](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [クラウド セキュリティ制御シリーズ: 保存時のデータの暗号化](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online がメールの機密情報をセキュリティで保護する方法](exchange-online-secures-email-secrets.md) <br/> [カスタマー キーによるサービスの暗号化](customer-key-overview.md) <br/> |
|ユーザー間で転送中のファイル。 これらのファイルには、ユーザー Office共有されるドキュメントや SharePoint リスト アイテムを含めることもできます。  <br/> |転送中のファイルの TLS  <br/> |[OneDrive for Business および SharePoint Online におけるデータ暗号化](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business Online: セキュリティとアーカイブ](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features) <br/> |
|受信者間の転送中の電子メール。 この電子メールには、Exchange Online によってホストされる電子メールが含まれます。  <br/> |Officeメールの Azure Rights Management、S/MIME、TLS による 365 メッセージの暗号化  <br/> |[Office 365 Message Encryption (OME)](ome.md) <br/> [Office 365 での電子メールの暗号化](email-encryption.md) <br/> [Exchange Online が TLS を使って Office 365 のメール接続をセキュリティで保護する方法](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Microsoft Teams を使用して受信者間で転送中のチャット、メッセージ、ファイル。 <br/> |Teams は TLS と MTLS を使用してインスタント メッセージを暗号化します。 メディア トラフィックは、Secure RTP (SRTP) を使用して暗号化されます。 Teams は、暗号化キー交換に FIPS (連邦情報処理標準) 準拠のアルゴリズムを使用します。 <br/> |[Teams の暗号化](/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>セキュリティとコンプライアンスの要件を満たすために暗号化を詳細に制御する必要がある場合は、どうしますか?

Microsoft 365 は、ボリューム暗号化、ファイル暗号化、およびメールボックスの暗号化に関する Microsoft が管理するソリューションを 365 Officeします。 さらに、Microsoft には、管理および制御できる暗号化ソリューションが提供されています。 これらの暗号化ソリューションは、Azure 上に構築されています。
  
詳細については、次のリソースを参照してください。
  
- [Azure Active Directory Rights Management の概要](/information-protection/understand-explore/what-is-azure-rms)

- [管理センターで Rights Management をアクティブ化する](../enterprise/activate-rms-in-microsoft-365.md)

- [SharePoint 管理センターで Information Rights Management (IRM) を設定する](set-up-irm-in-sp-admin-center.md)

- [Office 365 のカスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [Microsoft 365 のダブル キー暗号化](double-key-encryption.md)

## <a name="how-do-i"></a>方法

|**このタスクを実行するには**|**これらのリソースを参照してください。**|
|:-----|:-----|
|組織の暗号化を設定する  <br/> |[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md) <br/> |
|証明書、テクノロジ、TLS 暗号スイートの詳細を表示する <br/> |[暗号化に関する技術的な詳細](technical-reference-details-about-encryption.md) <br/> |
|モバイル デバイスで暗号化されたメッセージを処理する  <br/> |[暗号化されたメッセージを Android デバイスで表示する](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [iPhone または iPad で暗号化されたメッセージを表示する](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|パスワード保護を使用してドキュメントを暗号化する  <br/><br/>  パスワード保護はブラウザーではサポートされていません。 パスワード保護には、デスクトップ バージョンの Word、Excel、PowerPoint を使用します。 |[ドキュメント、ブック、またはプレゼンテーションの保護を追加または削除する](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> [保護の **追加] セクションを** 選択し、「パスワードで暗号化 **する」を参照してください**。  |
|ドキュメントから暗号化を削除する  <br/> |[ドキュメント、ブック、またはプレゼンテーションの保護を追加または削除する](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> [保護の **削除] セクションを** 選択し、「パスワード暗号化の削除 **」を参照してください**。  |


## <a name="related-topics"></a>関連項目

[Microsoft 365 のセキュリティと情報保護の機能を計画する](plan-for-security-and-compliance.md)

[ビジネス プラン用の Microsoft 365 をセキュリティで保護する上位 10 の方法](/office365/admin/security-and-compliance/secure-your-business-data)

[Microsoft Stream Video レベルの暗号化と再生フロー](/stream/network-overview#video-level-encryption-and-playback-flow)
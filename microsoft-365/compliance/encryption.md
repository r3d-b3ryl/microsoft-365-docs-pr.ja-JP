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
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365solution-mip
- m365initiative-compliance
description: Office 365を使用すると、コンテンツは保存時および転送中に暗号化され、使用可能な最も強力な暗号化、プロトコル、テクノロジが使用できます。 Office 365での暗号化の概要を確認します。
ms.openlocfilehash: 5b7b0f9fecbcbb6150eb56e19757c954aeb3e812
ms.sourcegitcommit: db1e48af88995193f15bbd5962f5101a6088074b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65637475"
---
# <a name="encryption"></a>暗号化

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

暗号化は、ファイル保護と情報保護戦略の重要な部分です。 この記事では、Office 365の暗号化の概要について説明します。 組織の暗号化を設定する方法や、Officeドキュメントをパスワードで保護する方法などの暗号化タスクに関するヘルプを参照してください。
  
- TLS などの証明書とテクノロジの詳細については、「[Office 365での暗号化に関する技術リファレンスの詳細](technical-reference-details-about-encryption.md)」を参照してください。

- 組織の暗号化を構成または設定する方法については、「[Office 365 Enterpriseでの暗号化の設定](set-up-encryption.md)」を参照してください。

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>暗号化とは何か、Office 365ではどのように機能しますか?

暗号化プロセスでは、データ (プレーンテキストと呼ばれます) が暗号テキストにエンコードされます。 プレーンテキストとは異なり、暗号化テキストが暗号化解除されるまで、人やコンピューターでは暗号テキストを使用できません。 復号化には、承認されたユーザーのみが持つ暗号化キーが必要です。 暗号化を使用すると、承認された受信者のみがコンテンツの暗号化を解除できるようになります。 コンテンツには、ファイル、電子メール メッセージ、予定表エントリなどが含まれます。
  
暗号化自体では、コンテンツの傍受は防止されません。 暗号化は、組織の大規模な情報保護戦略の一部です。 暗号化を使用すると、承認された当事者のみが暗号化されたデータを使用できるようになります。
  
同時に複数の暗号化レイヤーを配置できます。 たとえば、電子メール メッセージと、電子メールが流れる通信チャネルを暗号化できます。 Office 365では、いくつかの強力な暗号化プロトコルと、トランスポート層のセキュリティ/セキュリティで保護されたソケット層 (TLS/SSL)、インターネット プロトコル セキュリティ (IPSec)、高度な暗号化標準 (AES) を含むテクノロジを使用して、保存時と転送中にデータが暗号化されます。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>保存データと転送中のデータの暗号化

 **保存データの例には**、SharePoint ライブラリにアップロードしたファイル、Project Online データ、Skype for Business会議でアップロードしたドキュメント、メールボックス内のフォルダーに保存したメール メッセージと添付ファイル、アップロード先のファイルなどがあります。OneDrive for Business。
  
 **転送中のデータの例には** 、配信中のメール メッセージや、オンライン会議で行われる会話などがあります。 Office 365では、ユーザーのデバイスが Microsoft サーバーと通信しているとき、または Microsoft サーバーが別のサーバーと通信しているときは、データが転送されます。
  
Office 365では、複数のレイヤーと種類の暗号化が連携してデータをセキュリティで保護します。 次の表に、追加情報へのリンクを含む例をいくつか示します。
  
|**コンテンツの種類**|**暗号化テクノロジ**|**追加情報**|
|:-----|:-----|:-----|
|デバイス上のファイル。 これらのファイルには、フォルダーに保存された電子メール メッセージ、コンピューター、Tablet PC、または電話に保存されたドキュメントOffice、Microsoft クラウドに保存されたデータを含めることができます。  <br/> |Microsoft データセンターの BitLocker。 BitLocker は、クライアント コンピューター (Windows コンピューターやタブレットなど) でも使用できます。  <br/> Microsoft データセンター内の分散キー マネージャー (DKM)  <br/> Microsoft 365の顧客キー  <br/> |[Windows IT センター: BitLocker](/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft トラスト センター: 暗号化](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [クラウド セキュリティ 制御シリーズ: 保存データの暗号化](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online がメールの機密情報をセキュリティで保護する方法](exchange-online-secures-email-secrets.md) <br/> [カスタマー キーによるサービスの暗号化](customer-key-overview.md) <br/> |
|ユーザー間で転送中のファイル。 これらのファイルには、Officeドキュメントや、ユーザー間で共有SharePointリスト アイテムを含めることができます。  <br/> |転送中のファイルの TLS  <br/> |[OneDrive for Business および SharePoint Online におけるデータ暗号化](data-encryption-in-odb-and-spo.md) <br/> [オンラインSkype for Business: セキュリティとアーカイブ](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features) <br/> |
|受信者間の転送中の電子メール。 この電子メールには、Exchange Onlineがホストする電子メールが含まれます。  <br/> |転送中の電子メールの Azure Rights Management、S/MIME、TLS を使用したMicrosoft Purview Message Encryption  <br/> |[メッセージ暗号化](ome.md) <br/> [Office 365 での電子メールの暗号化](email-encryption.md) <br/> [Exchange Online が TLS を使って Office 365 のメール接続をセキュリティで保護する方法](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Microsoft Teamsを使用して受信者間で転送中のチャット、メッセージ、ファイル。 <br/> |Teamsでは、TLS と MTLS を使用してインスタント メッセージを暗号化します。 メディア トラフィックは、Secure RTP (SRTP) を使用して暗号化されます。 Teamsでは、暗号化キー交換に FIPS (連邦情報処理標準) 準拠アルゴリズムが使用されます。 <br/> |[Teamsの暗号化](/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>セキュリティとコンプライアンスの要件を満たすために暗号化をより細かく制御する必要がある場合はどうなりますか?

Microsoft 365では、ボリューム暗号化、ファイル暗号化、メールボックス暗号化をOffice 365で Microsoft が管理するソリューションを提供します。 さらに、Microsoft では、管理および制御できる暗号化ソリューションを提供しています。 これらの暗号化ソリューションは、Azure 上に構築されています。
  
詳細については、次のリソースを参照してください。
  
- [Azure Active Directory Rights Management の概要](/information-protection/understand-explore/what-is-azure-rms)

- [管理センターでRights Managementをアクティブ化する](../enterprise/activate-rms-in-microsoft-365.md)

- [SharePoint 管理センターで Information Rights Management (IRM) を設定する](set-up-irm-in-sp-admin-center.md)

- [Microsoft Purview カスタマー キーを使用したサービスの暗号化](customer-key-overview.md)

- [二重キー暗号化](double-key-encryption.md)

## <a name="how-do-i"></a>方法

|**このタスクを実行するには**|**これらのリソースを確認する**|
|:-----|:-----|
|組織の暗号化を設定する|[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md)|
|証明書、テクノロジ、TLS 暗号スイートに関する詳細を表示する|[暗号化に関する技術的な詳細](technical-reference-details-about-encryption.md)|
|モバイル デバイスで暗号化されたメッセージを操作する|[Android deviceView で暗号化されたメッセージをiPhone](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)[またはiPadに](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)表示する|
|パスワード保護を使用してドキュメントを暗号化します。 (パスワード保護はブラウザーではサポートされていません。 パスワード保護には、デスクトップ バージョンの Word、Excel、PowerPointを使用します)。 |[ドキュメント、ブック、またはプレゼンテーションの保護を追加または削除します](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)。 [ **保護の追加]** セクションを選択し、 **パスワードで暗号化** するに関するセクションを参照してください。|
|ドキュメントから暗号化を削除する|[ドキュメント、ブック、またはプレゼンテーションの保護を追加または削除します](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)。 [ **保護の削除]** セクションを選択し、 **パスワード暗号化の削除** に関するセクションを参照してください。  |

## <a name="related-topics"></a>関連項目

[Microsoft 365セキュリティと情報保護機能を計画する](plan-for-security-and-compliance.md)

[ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](/office365/admin/security-and-compliance/secure-your-business-data)

[Microsoft Stream ビデオ レベルの暗号化と再生フロー](/stream/network-overview#video-level-encryption-and-playback-flow)

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
description: このOffice 365コンテンツは、利用可能な最も強力な暗号化、プロトコル、およびテクノロジを使用して、保存時および転送中に暗号化されます。 暗号化の概要については、Office 365。
ms.openlocfilehash: c54508434c5ae5126a79eba1cb6dab3851d8f746
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59175959"
---
# <a name="encryption"></a>暗号化

暗号化は、ファイル保護と情報保護戦略の重要な部分です。 この記事では、暗号化の概要について説明Office 365。 組織の暗号化を設定する方法や、ドキュメントをパスワードで保護する方法など、暗号化タスクOfficeしてください。
  
- TLS などの証明書とテクノロジの詳細については、「暗号化[に関](technical-reference-details-about-encryption.md)するテクニカル リファレンスの詳細」を参照Office 365。

- 組織の暗号化を構成または設定する方法については、「暗号化を構成する」を参照[Office 365 Enterprise。](set-up-encryption.md)

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>暗号化とは何か、および暗号化の動作Office 365。

暗号化プロセスは、データ (プレーン テキストと呼ばれます) を暗号テキストにエンコードします。 プレーン テキストとは異なり、暗号テキストが暗号化解除されるまでは、暗号化テキストをユーザーまたはコンピューターで使用できません。 復号化には、承認されたユーザーのみが持つ暗号化キーが必要です。 暗号化を使用すると、承認された受信者のみがコンテンツを解読できます。 コンテンツには、ファイル、電子メール メッセージ、予定表エントリなどがあります。
  
暗号化自体では、コンテンツの傍受は防止しません。 暗号化は、組織のより大きな情報保護戦略の一部です。 暗号化を使用すると、承認された関係者のみが暗号化されたデータを使用できます。
  
複数の暗号化レイヤーを同時に設定できます。 たとえば、電子メール メッセージと、電子メールが流れる通信チャネルも暗号化できます。 Office 365 を使用すると、データは、いくつかの強力な暗号化プロトコルと、トランスポート層セキュリティ/Secure Sockets Layer (TLS/SSL)、インターネット プロトコル セキュリティ (IPSec)、および高度暗号化標準 (AES) を含むテクノロジを使用して、保存時および転送中に暗号化されます。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>保存中のデータと転送中のデータの暗号化

 保存中のデータの例には、SharePoint ライブラリにアップロードしたファイル、Project Online データ、Skype for Business 会議にアップロードしたドキュメント、メールボックス内のフォルダーに保存した電子メール メッセージと添付ファイル、OneDrive for Business にアップロードしたファイルが含まれます。
  
 **転送中のデータの例** としては、配信中のメール メッセージや、オンライン会議で行う会話があります。 このOffice 365、ユーザーのデバイスが Microsoft サーバーと通信している場合、または Microsoft サーバーが別のサーバーと通信している場合、データは転送中です。
  
このOffice 365、複数のレイヤーと種類の暗号化が一緒に機能し、データを保護します。 次の表に、追加情報へのリンクを含むいくつかの例を示します。
  
|**コンテンツの種類**|**暗号化テクノロジ**|**追加情報**|
|:-----|:-----|:-----|
|デバイス上のファイル。 これらのファイルには、フォルダーに保存された電子メール メッセージ、Officeタブレット、または電話に保存されたドキュメント、または Microsoft クラウドに保存されたデータが含まれます。  <br/> |Microsoft データセンターの BitLocker。 BitLocker は、コンピューターやタブレットなどのクライアント コンピューター Windows使用することもできます。  <br/> Microsoft データセンターの分散キー マネージャー (DKM)  <br/> 顧客キーのMicrosoft 365  <br/> |[WindowsIT センター: BitLocker](/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft Trust Center: 暗号化](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [クラウド セキュリティ制御シリーズ: 保存時のデータの暗号化](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online がメールの機密情報をセキュリティで保護する方法](exchange-online-secures-email-secrets.md) <br/> [カスタマー キーによるサービスの暗号化](customer-key-overview.md) <br/> |
|ユーザー間で転送中のファイル。 これらのファイルには、ユーザー Office共有されるSharePointリスト アイテムを含めることもできます。  <br/> |転送中のファイルの TLS  <br/> |[OneDrive for Business および SharePoint Online におけるデータ暗号化](data-encryption-in-odb-and-spo.md) <br/> [Skype for Businessオンライン: セキュリティとアーカイブ](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features) <br/> |
|受信者間の転送中の電子メール。 この電子メールには、ユーザーがホストする電子メールExchange Online。  <br/> |Office 365 Message Encryptionメールの Azure Rights Management、S/MIME、TLS を使用したメールの送信  <br/> |[Office 365 Message Encryption (OME)](ome.md) <br/> [Office 365 での電子メールの暗号化](email-encryption.md) <br/> [Exchange Online が TLS を使って Office 365 のメール接続をセキュリティで保護する方法](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|メッセージを使用して受信者間で転送中のチャット、メッセージ、およびMicrosoft Teams。 <br/> |Teams TLS と MTLS を使用してインスタント メッセージを暗号化します。 メディア トラフィックは、Secure RTP (SRTP) を使用して暗号化されます。 Teamsは、暗号化キー交換に FIPS (連邦情報処理標準) 準拠のアルゴリズムを使用します。 <br/> |[ユーザーの暗号化Teams](/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>セキュリティとコンプライアンスの要件を満たすために暗号化を詳細に制御する必要がある場合は、どうしますか?

Microsoft 365は、ボリューム暗号化、ファイル暗号化、およびメールボックスの暗号化に関する Microsoft が管理するソリューションを提供Office 365。 さらに、Microsoft には、管理および制御できる暗号化ソリューションが提供されています。 これらの暗号化ソリューションは、Azure 上に構築されています。
  
詳細については、次のリソースを参照してください。
  
- [Azure Active Directory Rights Management の概要](/information-protection/understand-explore/what-is-azure-rms)

- [管理センターで Rights Management をアクティブ化する](../enterprise/activate-rms-in-microsoft-365.md)

- [SharePoint 管理センターで Information Rights Management (IRM) を設定する](set-up-irm-in-sp-admin-center.md)

- [Office 365 のカスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [ユーザーのダブル キー暗号化Microsoft 365](double-key-encryption.md)

## <a name="how-do-i"></a>方法

|**このタスクを実行するには**|**これらのリソースを参照してください。**|
|:-----|:-----|
|組織の暗号化を設定する  <br/> |[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md) <br/> |
|証明書、テクノロジ、TLS 暗号スイートの詳細を表示する <br/> |[暗号化に関する技術的な詳細](technical-reference-details-about-encryption.md) <br/> |
|モバイル デバイスで暗号化されたメッセージを処理する  <br/> |[暗号化されたメッセージを Android デバイスで表示する](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [iPhone または iPad で暗号化されたメッセージを表示する](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|パスワード保護を使用してドキュメントを暗号化する  <br/><br/>  パスワード保護はブラウザーではサポートされていません。 パスワード保護には、デスクトップ バージョンの Word、Excel、PowerPointを使用します。 |[ドキュメント、ブック、またはプレゼンテーションの保護を追加または削除する](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> [保護の **追加] セクションを** 選択し、「パスワードで暗号化 **する」を参照してください**。  |
|ドキュメントから暗号化を削除する  <br/> |[ドキュメント、ブック、またはプレゼンテーションの保護を追加または削除する](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> [保護の **削除] セクションを** 選択し、「パスワード暗号化の削除 **」を参照してください**。  |


## <a name="related-topics"></a>関連項目

[セキュリティとMicrosoft 365機能の計画](plan-for-security-and-compliance.md)

[ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](/office365/admin/security-and-compliance/secure-your-business-data)

[Microsoft Stream Video レベルの暗号化と再生フロー](/stream/network-overview#video-level-encryption-and-playback-flow)
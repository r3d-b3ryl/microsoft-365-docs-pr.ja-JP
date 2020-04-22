---
title: 暗号化
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
description: Office 365 では、使用可能な暗号化、プロトコル、およびテクノロジが最強の状態で、コンテンツが保存され、転送中に暗号化されます。 Office 365 の暗号化の概要について説明します。
ms.openlocfilehash: fdd1c50c7fde1892b5bab4ad83cddf8e032f4d61
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631682"
---
# <a name="encryption"></a>暗号化

暗号化は、ファイル保護と情報保護戦略の重要な部分です。 この記事では、Office 365 の暗号化の概要について説明します。 組織のために暗号化を設定する方法と、Office ドキュメントをパスワードで保護する方法など、暗号化タスクに関するヘルプを表示します。
  
- TLS などの証明書とテクノロジの詳細については、「 [Office 365 の暗号化に関する技術リファレンスの詳細](technical-reference-details-about-encryption.md)」を参照してください。

- 組織の暗号化を構成または設定する方法については、「 [Office 365 Enterprise で暗号化を設定](set-up-encryption.md)する」を参照してください。

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>暗号化とは何ですか。 Office 365 ではどのように動作しますか?

暗号化プロセスは、データ (プレーンテキストと呼ばれる) を暗号テキストにエンコードします。 プレーンテキストとは異なり、暗号化テキストは、暗号化テキストが復号化されるまで、またはユーザーまたはコンピューターで使用できません。 復号化には、承認されたユーザーのみが所有する暗号化キーが必要です。 暗号化を使用すると、承認された受信者のみがコンテンツを解読できるようになります。 コンテンツには、ファイル、電子メールメッセージ、予定表エントリなどが含まれます。
  
暗号化だけではコンテンツの傍受を防ぐことはできません。 暗号化は、組織にとってより大きな情報保護戦略の一部となります。 暗号化を使用すると、認証されたパーティのみが暗号化されたデータを使用できるようになります。
  
一度に複数の暗号化レイヤーを設定することができます。 たとえば、電子メールメッセージと、電子メールがフローする通信チャネルも暗号化できます。 Office 365 では、データは保存時と転送中に暗号化され、複数の強力な暗号化プロトコルと、トランスポート層セキュリティ/Secure Sockets Layer (TLS/SSL)、インターネットプロトコルセキュリティ (IPSec)、Advanced Encryption Standard (AES) を含むテクノロジが使用されます。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>保存中のデータと転送中のデータの暗号化

 保存されていない**データの例**としては、SharePoint ライブラリにアップロードしたファイル、プロジェクトオンラインデータ、Skype for business 会議にアップロードした電子メールメッセージと添付ファイル、および OneDrive for business にアップロードしたファイルなどがあります。
  
 **転送中のデータの例**には、配信処理中のメールメッセージ、またはオンライン会議で行われている会話が含まれます。 Office 365 では、ユーザーのデバイスが Microsoft サーバーと通信している場合、または Microsoft サーバーが他のサーバーと通信している場合に、データが転送されます。
  
Office 365 では、複数のレイヤーと暗号化の種類が連携してデータを保護します。 次の表に、いくつかの例を示し、追加情報へのリンクを掲載しています。
  
|**コンテンツの種類**|**暗号化テクノロジ**|**追加情報**|
|:-----|:-----|:-----|
|デバイス上のファイル。 これらのファイルには、フォルダーに保存された電子メールメッセージ、コンピューター、タブレット、電話に保存された Office ドキュメント、または Microsoft クラウドに保存されたデータを含めることができます。  <br/> |Microsoft データセンター内の BitLocker。 BitLocker は、Windows コンピューターやタブレットなどのクライアントマシンでも使用できます。  <br/> Microsoft データセンターでの Distributed Key Manager (DKM)  <br/> Microsoft 365 の顧客キー  <br/> |[Windows IT センター: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft セキュリティセンター: 暗号化](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [Cloud security controls series: 休息中のデータを暗号化する](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online がメールの機密情報をセキュリティで保護する方法](exchange-online-secures-email-secrets.md) <br/> [顧客キーによるサービスの暗号化](customer-key-overview.md) <br/> |
|ユーザー間で転送中のファイル。 これらのファイルには、ユーザー間で共有する Office ドキュメントまたは SharePoint リストアイテムを含めることができます。  <br/> |送信中のファイルの TLS  <br/> |[OneDrive for Business および SharePoint Online におけるデータ暗号化](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business Online: セキュリティとアーカイブ](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|受信者間で送信中の電子メール。 このメールには、Exchange Online によってホストされる電子メールが含まれます。  <br/> |送信中の電子メールのための Azure Rights Management、S/MIME、TLS を使用した Office 365 メッセージの暗号化  <br/> |[Office 365 Message Encryption (OME)](ome.md) <br/> [Office 365 での電子メールの暗号化](email-encryption.md) <br/> [Exchange Online が TLS を使って Office 365 のメール接続をセキュリティで保護する方法](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>セキュリティとコンプライアンスの要件を満たすために、暗号化についてより詳細に制御する必要がある場合はどうすればよいですか?

Microsoft 365 では、Office 365 でのボリューム暗号化、ファイル暗号化、メールボックス暗号化用の Microsoft 管理ソリューションが提供されています。 さらに、Microsoft では、管理および制御できる暗号化ソリューションを提供しています。 これらの暗号化ソリューションは Azure に基づいて構築されています。
  
詳細については、次のリソースを参照してください。
  
- [Azure Active Directory Rights Management の概要](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [管理センターで Rights Management をアクティブ化する](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)

- [Office 365 の顧客キーによるサービスの暗号化](customer-key-overview.md)

## <a name="how-do-i"></a>方法

|**このタスクを実行するには**|**次のリソースを参照**|
|:-----|:-----|
|組織の暗号化の設定  <br/> |[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md) <br/> |
|証明書、テクノロジ、TLS 暗号スイートに関する詳細を表示する <br/> |[暗号化に関する技術的な詳細](technical-reference-details-about-encryption.md) <br/> |
|モバイルデバイスで暗号化されたメッセージを操作する  <br/> |[暗号化されたメッセージを Android デバイスで表示する](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [iPhone または iPad で暗号化されたメッセージを表示する](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|パスワード保護を使用してドキュメントを暗号化する  <br/><br/>  ブラウザーでは、パスワード保護はサポートされていません。 デスクトップ版の Word、Excel、および PowerPoint をパスワード保護に使用します。 |[文書、ブック、またはプレゼンテーションの保護を追加または削除する](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> [**保護の追加**] セクションを選択し、[**パスワードで暗号化**する] をクリックします。  |
|文書から暗号化を削除する  <br/> |[文書、ブック、またはプレゼンテーションの保護を追加または削除する](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> [**保護の削除**] セクションを選択し、[**パスワード暗号化の解除**] をクリックします。  |

## <a name="related-topics"></a>関連項目

[Microsoft 365 のセキュリティおよび情報保護機能を計画する](plan-for-security-and-compliance.md)

[Microsoft 365 for business プランをセキュリティで保護するための10位の方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data?view=o365-worldwide)

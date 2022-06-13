---
title: 以前のバージョンのメッセージ暗号化用に Azure Rights Managementを設定する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: Office 365 メッセージ暗号化の以前のバージョンは、Microsoft Azure Rights Management (以前は Windows Azure Active Directory Rights Management と呼ばられていました) によって異なります。
ms.openlocfilehash: 66447d601d86f1863cf060a3ad097686bb58be98
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66016242"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>以前のバージョンのメッセージ暗号化用に Azure Rights Managementを設定する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

このトピックでは、以前のバージョンの Office 365 Message Encryption (OME) で使用するために、Azure Information Protectionの一部である Azure Rights Management (RMS) をアクティブ化して設定するために従う必要がある手順について説明します。

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>この記事は、以前のバージョンの OME にのみ適用されます

組織を Microsoft Purview Message Encryption にまだ移行していないが、既に OME を展開している場合は、この記事の情報が組織に適用されます。 Microsoft では、組織にとって妥当な場合は、すぐに Microsoft Purview Message Encryption に移行する計画を立てるようお勧めします。 手順については、「 [Microsoft Purview メッセージ暗号化の設定](set-up-new-message-encryption-capabilities.md)」を参照してください。 新機能の最初の動作の詳細については、「 [メッセージの暗号化](ome.md)」を参照してください。 この記事の残りの部分では、Microsoft Purview メッセージ暗号化のリリース前の OME 動作について説明します。

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>以前のバージョンの Office 365 メッセージ暗号化を使用するための前提条件
<a name="warmprereqs"> </a>

IRM を含む Office 365 メッセージ暗号化 (OME) は、Azure Rights Management (Azure RMS) によって異なります。 Azure RMS は、Azure Information Protectionで使用される保護テクノロジです。 OME を使用するには、組織に、Azure Rights Management サブスクリプションを含むExchange OnlineまたはExchange Online Protectionサブスクリプションを含める必要があります。

- サブスクリプションに何が含まれているかわからない場合は、[メッセージ ポリシー、回復、コンプライアンス](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)に関するExchange Onlineサービスの説明を参照してください。

- Azure Rights Managementをお持ちで、Exchange OnlineまたはExchange Online Protection用に設定されていない場合、この記事では Azure Rights Managementをアクティブ化する方法と、Azure で動作するように OME を設定する最適な方法について説明しますRights Management。

- Exchange OnlineまたはExchange Online Protection用に Azure Rights Managementを使用するように OME を既に設定している場合は、セットアップ方法によっては、すぐに OME とその新機能の使用を開始できる可能性があります。 この記事では、OME を正しく設定したかどうかを判断する方法、セットアップを変更する必要がある場合の対処方法、およびセットアップを変更しないことを選択した場合の動作について説明します。 たとえば、新しい機能を使用するには、OME で Azure RMS を使用する必要があります。 オンプレミスの Active Directory RMS では新しい機能を使用できません。

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Office 365で以前のバージョンの OME に対して Azure Rights Managementをアクティブ化する

組織内のユーザーが送信するメッセージに情報保護を適用し、Azure Rights Management サービスによって保護されているメッセージとファイルを開くことができるように、Azure Rights Managementをアクティブ化する必要があります。 手順については、「[Azure Rights Managementのアクティブ化](/azure/information-protection/activate-service)」を参照してください。 アクティブ化が完了したら、ここに戻り、この記事のタスクを続行します。

## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>信頼された発行ドメイン (TPD) をインポートして Azure RMS を使用するように以前のバージョンの OME を設定する

TPD は、組織の権限管理設定に関する情報を含む XML ファイルです。 たとえば、TPD には、証明書とライセンスの署名と暗号化に使用されるサーバー ライセンサー証明書 (SLC)、ライセンスと発行に使用される URL などに関する情報が含まれています。 PowerShell を使用して、組織に TPD をインポートします。

> [!IMPORTANT]
> 以前は、Active Directory Rights Management サービス (AD RMS) から組織に TPD をインポートすることを選択できました。 ただし、この操作を行うと、Microsoft Purview メッセージ暗号化を使用できなくなるため、お勧めしません。 組織が現在このように構成されている場合は、オンプレミスの Active Directory RMS からクラウドベースの Azure Information Protectionに移行する計画を作成することをお勧めします。 詳細については、「[AD RMS から Azure Information Protectionへの移行](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)」を参照してください。 Azure Information Protectionへの移行が完了するまで、Microsoft Purview Message Encryption を使用することはできません。

**Azure RMS から TPD をインポートするには:**

1. [Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 組織の地理的な場所に対応するキー共有 URL を選択します。

   |場所|キー共有の場所の URL|
   |---|---|
   |北アメリカ|<https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc>|
   |欧州連合|<https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc>|
   |アジア|<https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc>|
   |南アメリカ|<https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc>|
   |行政機関向け Office 365 (行政機関のコミュニティ クラウド)  <br/> この RMS キー共有の場所は、政府機関 SKU のOffice 365を購入したお客様向けに予約されています。|<https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc>|

3. [次のように Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) コマンドレットを実行して、キー共有の場所を構成します。

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```

   たとえば、組織が北米にある場合にキー共有の場所を構成するには、次のようにします。

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. -RMSOnline スイッチを使用[して Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) コマンドレットを実行して、Azure Rights Managementから TPD をインポートします。

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   *ここで、TPDName* は TPD に使用する名前です。 たとえば、"Contoso North American TPD" とします。

5. Azure Rights Management サービスを使用するように組織が正常に構成されたことを確認するには、次のように -RMSOnline スイッチを使用して [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) コマンドレットを実行します。

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   特に、このコマンドレットは、Azure Rights Management サービスとの接続をチェックし、TPD をダウンロードし、その有効性を確認します。

6. 次のように [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) コマンドレットを実行して、azure Rights Management テンプレートをOutlook on the webおよびOutlookで使用できないようにします。

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. 次のように [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) コマンドレットを実行して、クラウドベースの電子メール組織の Azure Rights Managementを有効にし、メッセージ暗号化に Azure Rights Managementを使用するように構成Office 365。

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. TPD が正常にインポートされ、Azure Rights Managementが有効になっていることを確認するには、Test-IRMConfiguration コマンドレットを使用して Azure Rights Management機能をテストします。 詳細については、 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) の「例 1」を参照してください。

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>以前のバージョンの OME を Active Directory でセットアップRights Management Azure Information Protectionではありません。どうすればよいですか?
<a name="importTPDs"> </a>

Active Directory Rights Managementでは、既存のOffice 365メッセージ暗号化メール フロー ルールを引き続き使用できますが、Microsoft Purview Message Encryption を構成したり使用したりすることはできません。 代わりに、Azure Information Protectionに移行する必要があります。 移行と組織にとっての意味については、「[AD RMS から Azure Information Protectionへの移行](/information-protection/deploy-use/prepare-environment-adrms)」を参照してください。

## <a name="next-steps"></a>次の手順
<a name="importTPDs"> </a>

Azure Rights Managementのセットアップが完了したら、Microsoft Purview メッセージ暗号化を有効にする場合は、「[Microsoft Purview メッセージ暗号化のセットアップ](./set-up-new-message-encryption-capabilities.md)」を参照してください。

Microsoft Purview Message Encryption を使用するように組織を設定したら、 [メール フロー ルールを定義](define-mail-flow-rules-to-encrypt-email.md)する準備が整いました。

## <a name="related-topics"></a>関連項目
<a name="importTPDs"> </a>

[Office 365 での暗号化](encryption.md)

[Office 365 の暗号化についてのテクニカル リファレンスの詳細](technical-reference-details-about-encryption.md)

[Azure Active Directory Rights Management の概要](/information-protection/understand-explore/what-is-azure-rms)

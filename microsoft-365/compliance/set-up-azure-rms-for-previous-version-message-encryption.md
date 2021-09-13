---
title: 以前のバージョンのメッセージ暗号化用に Azure Rights Management を設定する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 以前のバージョンの Office 365 Message Encryptionは、Microsoft Azure Rights Management (以前は Windows Azure Active Directory Rights Management) に依存します。
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216424"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>以前のバージョンのメッセージ暗号化用に Azure Rights Management を設定する

このトピックでは、以前のバージョンの Office 365 Message Encryption (OME) で使用するために Azure Information Protection の一部である Azure Rights Management (RMS) をアクティブ化してセットアップするために従う必要がある手順について説明します。

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>この記事は、以前のバージョンの OME にのみ適用されます。

組織を新しい OME 機能にまだ移動していないが、既に OME を展開している場合は、この記事の情報が組織に適用されます。 Microsoft では、組織に妥当な場合は、すぐに新しい OME 機能に移行する計画を立てをお勧めします。 手順については、「新しい機能を[セットアップする」をOffice 365 Message Encryptionしてください](set-up-new-message-encryption-capabilities.md)。 新しい機能の最初の動作の詳細については、「Office 365 Message Encryption」[を参照してください](ome.md)。 この記事の残りの部分は、新しい OME 機能のリリース前の OME 動作を参照します。

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>以前のバージョンのサーバーを使用するための前提条件Office 365 Message Encryption
<a name="warmprereqs"> </a>

Office 365 Message Encryption (OME) は、Azure Rights Management (Azure RMS) によって異なります。 Azure RMS は、Azure Information Protection で使用される保護テクノロジです。 OME を使用するには、組織に Azure Rights Management サブスクリプションExchange Onlineまたは Exchange Online Protectionサブスクリプションを含める必要があります。
  
- サブスクリプションに含まれる内容が不明な場合は、「メッセージ ポリシー、回復、およびコンプライアンスExchange Onlineサービスの説明」[を参照してください](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。

- Azure Rights Management を使用しているが、Exchange Online または Exchange Online Protection に対して設定されていない場合、この記事では Azure Rights Management をアクティブ化する方法と、Azure Rights Management で動作するように OME をセットアップする最適な方法について説明します。

- Exchange Online または Exchange Online Protection の Azure Rights Management を使用するように OME を既にセットアップしている場合は、設定方法に応じて、すぐに OME とその新しい機能の使用を開始できます。 この記事では、OME を正しく設定したかどうかを判断する方法、セットアップを変更する必要がある場合の処理、セットアップを変更しない場合の処理について説明します。 たとえば、新しい機能を使用するには、Azure RMS と OME を使用する必要があります。 オンプレミスの Active Directory RMS では、新しい機能を使用することはできません。

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>以前のバージョンの OME に対して Azure Rights Management をアクティブ化Office 365

組織のユーザーが送信するメッセージに情報保護を適用し、Azure Rights Management サービスによって保護されているメッセージとファイルを開くことができるので、Azure Rights Management をアクティブ化する必要があります。 手順については [、「Azure Rights Management のアクティブ化」を参照してください](/azure/information-protection/activate-service)。 ライセンス認証が完了したら、ここに戻り、この記事のタスクを続行します。
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>信頼できる発行ドメイン (TPD) をインポートして Azure RMS を使用するように以前のバージョンの OME をセットアップする

TPD は、組織の権限管理設定に関する情報を含む XML ファイルです。 たとえば、TPD には、証明書とライセンスの署名と暗号化に使用されるサーバー ライセンサー証明書 (SLC)、ライセンスおよび発行に使用される URL に関する情報が含まれています。 TPD を組織にインポートするには、次のWindows PowerShell。
  
> [!IMPORTANT]
> 以前は、Active Directory Rights Management サービス (RMS) から組織に TPD をインポートAD選択できます。 ただし、そうすると、新しい OME 機能を使用できないので、お勧めしません。 組織が現在この方法で構成されている場合は、オンプレミスの Active Directory RMS からクラウドベースの Azure Information Protection に移行する計画を作成するようにお勧めします。 詳細については、「RMS から Azure Information Protection への [移行AD」を参照してください](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。 Azure Information Protection への移行が完了するまで、新しい OME 機能を使用することはできません。
  
 **Azure RMS から TPD をインポートするには**
  
1. [Connect PowerShell をExchange Onlineする方法について説明します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 組織の地理的な場所に対応するキー共有 URL を選択します。

|**Location**|**キー共有場所の URL**|
|:-----|:-----|
|北アメリカ  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|欧州連合  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|アジア  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|南アメリカ  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|行政機関向け Office 365 (行政機関のコミュニティ クラウド)  <br/> この RMS キー共有の場所は、政府機関向け SKU 用にOffice 365予約されています。  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)コマンドレットを次のように実行して、キー共有の場所を構成します。 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   たとえば、組織が北アメリカにある場合にキー共有の場所を構成するには、次の手順を実行します。

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. -RMSOnline スイッチを使用 [して Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) コマンドレットを実行し、AZURE Rights Management から TPD をインポートします。 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   *TPDName* は、TPD に使用する名前です。 たとえば、「Contoso 北アメリカ TPD」とします。 

5. Azure Rights Management サービスを使用するように組織が正常に構成されたことを確認するには、次のように -RMSOnline スイッチを使用して [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) コマンドレットを実行します。

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   とりわけ、このコマンドレットは Azure Rights Management サービスとの接続をチェックし、TPD をダウンロードし、その有効性を確認します。

6. [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)コマンドレットを次のように実行して、Azure Rights Management テンプレートが Azure Rights Management テンプレートで使用Outlook on the web無効Outlook。 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)コマンドレットを次のように実行して、クラウドベースの電子メール組織で Azure Rights Management を有効にし、Azure Rights Management を使用するように構成Office 365 Message Encryption。

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. TPD を正常にインポートし、Azure Rights Management を有効にしたと確認するには、Test-IRMConfiguration コマンドレットを使用して Azure Rights Management の機能をテストします。 詳細については [、「Test-IRMConfiguration」の「例 1」を参照してください](/powershell/module/exchange/test-irmconfiguration)。

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>以前のバージョンの OME は、Azure Information Protection ではなく Active Directory Rights Management でセットアップされています。何をしますか?
<a name="importTPDs"> </a>

Active Directory Rights Management を使用して、既存Office 365 Message Encryptionメール フロー ルールを引き続き使用できますが、新しい OME 機能を構成または使用することはできません。 代わりに、Azure Information Protection に移行する必要があります。 組織の移行とこれが何を意味するのかについては、「RMS から Azure Information Protection への移行 [AD」を参照してください](/information-protection/deploy-use/prepare-environment-adrms)。
  
## <a name="next-steps"></a>次の手順
<a name="importTPDs"> </a>

Azure Rights Management のセットアップが完了したら、新しい OME 機能を有効にする場合は[、「Azure](./set-up-new-message-encryption-capabilities.md) Information Protection の上に構築された新しい Office 365 Message Encryption 機能をセットアップする」を参照してください。
  
新しい OME 機能を使用する組織をセットアップした後、新しい OME 機能を使用して電子メール メッセージを保護するためのメール フロー ルールを定義する [準備が整いました](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="related-topics"></a>関連項目
<a name="importTPDs"> </a>

[Office 365 での暗号化](encryption.md)
  
[Office 365 の暗号化についてのテクニカル リファレンスの詳細](technical-reference-details-about-encryption.md)
  
[Azure Active Directory Rights Management の概要](/information-protection/understand-explore/what-is-azure-rms)
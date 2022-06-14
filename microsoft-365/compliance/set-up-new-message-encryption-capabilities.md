---
title: Microsoft Purview のメッセージの暗号化を設定する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/16/2022
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 組織内外の相手と保護されたメールでコミュニケーションをとれるようにする、Microsoft Purview Message Encryption について説明します。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
- admindeeplinkEXCHANGE
ms.openlocfilehash: 48a5ca3bad7c0fb0d7120cb4e35bc5f24902a46e
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66043342"
---
# <a name="set-up-message-encryption"></a>Message Encryption を設定する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview Message Encryption により、保護されたメールをどのデバイスででも、誰とでも共有できるようになります。 Outlook.com や Gmail などのメール サービスを使用して、他の Microsoft 365 組織ともサードパーティとも、保護されたメッセージを交換できます。

お客様の組織で Microsoft Purview Message Encryption を使用できることを確認するには、以下の手順に従います。

## <a name="verify-that-azure-rights-management-is-active"></a>Azure Rights Management が有効であることを確認する

Microsoft Purview Message Encryption では、[Azure Rights Management Services (Azure RMS)](/azure/information-protection/what-is-information-protection) の保護機能が活用されています。Azure RMS は、暗号化とアクセス制御によってメールとドキュメントを保護するために、[Azure Information Protection](/azure/information-protection/what-is-azure-rms) によって使用されるテクノロジです。

Microsoft Purview Message Encryption の使用の前提条件は、お客様の組織のテナントで [Azure Rights Management](/azure/information-protection/what-is-azure-rms) をアクティブ化する必要があるということのみです。 それについては、Microsoft 365 によってメッセージの暗号化が自動的にアクティブ化されるため手動での操作は何も必要ありません。

Azure RMS は、ほとんどの対象プランでも自動的に有効化されるため、おそらくこの点についても何もする必要はありません。詳細については「[Azure Rights Management のアクティブ化](/azure/information-protection/activate-service)」に関するページを参照してください。

> [!IMPORTANT]
> Exchange Online で Active Directory Rights Management サービス (AD RMS) を使用する場合は、メッセージの暗号化を使用する前に [Azure Information Protection に移行する](/azure/information-protection/migrate-from-ad-rms-to-azure-rms)必要があります。 Microsoft Purview Message Encryption は AD RMS と互換性がありません。

詳しくは、以下を参照してください。

- サブスクリプション プランに Azure Information Protection (Azure RMS 機能を含む) が含まれているかどうかを確認するには、「[メッセージの暗号化についてよく寄せられる質問](ome-faq.yml)」を参照してください。
- 対象となるサブスクリプションの購入に関する情報については、「[Azure Information Protection](https://azure.microsoft.com/services/information-protection/)」を参照してください。

### <a name="manually-activating-azure-rights-management"></a>Azure Rights Management を手動で有効化する

Azure RMS を無効にした場合、または何らかの理由で自動的に有効化されなかった場合は、次のように手動で有効化できます:

- **Microsoft 365 管理センター**: 手順については、「[管理センターから Azure Rights Management を有効化する方法](/azure/information-protection/activate-office365)」を参照してください。
- **Azure Portal**: 手順については、「[Azure Portal から Azure Rights Management を有効化する方法](/azure/information-protection/activate-azure)」を参照してください。

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Azure Information Protection テナント キーの管理を構成する

この手順は省略可能です。 Microsoft が Azure Information Protection のルート キーを管理できるようにすることが既定であり、ほとんどの組織に推奨されるベスト プラクティスです。 このような場合は、何もする必要はありません。

コンプライアンス要件など、多くの理由により、独自のルート キー (Bring Your Own Key (BYOK) とも呼ばれる)の生成と管理が必要になる場合があります。 この場合には、Microsoft Purview Message Encryption を設定する前に、必要な手順を完了しておくことをお勧めします。 詳細については、「[Azure Information Protection テナント キーを計画して実装する](/information-protection/plan-design/plan-implement-tenant-key)」を参照してください。

## <a name="verify-microsoft-purview-message-encryption-configuration-in-exchange-online-powershell"></a>Exchange Online PowerShell で Microsoft Purview Message Encryption の構成を確認する

[Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell) で Microsoft Purview Message Encryption が使用されるように適切に Microsoft 365 テナントが構成されていることを確認できます。

1. Microsoft 365 テナントのグローバル管理者権限を持つアカウントを使用して、[Exchange Online PowerShell に接続](/powershell/exchange/connect-to-exchange-online-powershell)します。

2. Get-IRMConfiguration コマンドレットを実行します。

     AzureRMSLicensingEnabled パラメーターの値として $True が表示されます。これは、テナントで Microsoft Purview Message Encryption が構成されていることを示します。 そのように表示されない場合は、Set-IRMConfiguration で AzureRMSLicensingEnabled の値を $ True に設定して Microsoft Purview Message Encryption を有効にします。

3. 次の構文を使用して Test-IRMConfiguration コマンドレットを実行します:

   ```powershell
   Test-IRMConfiguration [-Sender <email address> -Recipient <email address>]
   ```

   **例**:

   ```powershell
   Test-IRMConfiguration -Sender securityadmin@contoso.com -Recipient securityadmin@contoso.com
   ```

   - 送信者と受信者の場合は、Microsoft 365 テナント内の任意のユーザーのメール アドレスを使用します。

     結果は次のようになります:

     ```console
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - *Contoso* は組織名に置き換えられます。

   - 既定のテンプレート名は、上に表示されているものとは異なる場合があります。 詳細については、「[Azure Information Protection のテンプレートを構成して管理する](/azure/information-protection/configure-policy-templates)」を参照してください。

4. **RMS テンプレートを取得できませんでした** というエラー メッセージが表示されてテストに合格しなかった場合は、次のコマンドを実行し、Test-IRMConfiguration コマンドレットを実行して合格を確認します。

   ```powershell
   $RMSConfig = Get-AadrmConfiguration
   $LicenseUri = $RMSConfig.LicensingIntranetDistributionPointUrl
   Set-IRMConfiguration -LicensingLocation $LicenseUri
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```
5. Rights Management サービスから切断するには、Remove-PSSession コマンドレットを実行します。

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-microsoft-purview-message-encryption"></a>次の手順: Microsoft Purview Message Encryption を使用するためのメール フロー ルールを定義する

メールを暗号化するためのメール フロー ルールをお客様の組織で以前に構成してある場合は、Microsoft Purview Message Encryption を使用するように既存のルールを更新する必要があります。 新しい展開の場合、新しいメール フロー ルールを作成する必要があります。

> [!IMPORTANT]
> 既存のメール フロー ルールを更新しないと、ユーザーは、新しいシームレスなエクスペリエンスではなく、引き続き、以前の HTML 添付ファイル形式を使用する暗号化されたメールを受信することになります。

メール フロー ルールは、メール メッセージを暗号化する条件、およびその暗号化を削除する条件を決定します。 ルールのアクションを設定すると、送信時に、ルールの条件に一致するすべてのメッセージが暗号化されます。

メッセージの暗号化のメール フロー ルールの作成手順については、「[Office 365 でメール メッセージを暗号化するためにメール フロー ルールを定義する](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

Microsoft Purview Message Encryption を使用するように既存のルールを更新するには:

1. Microsoft 365 管理センターから **[管理者]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">**[Exchange]**</a> の順に移動します。
2. Exchange 管理センターで、[**メール フロー]、[ルール**] の順に移動します。
3. ルールごとに、**次の操作を行います**:
    - [**メッセージのセキュリティを変更する**] を選択します。
    - [**Office 365 Message Encryption および適切な保護を適用する**] を選択します。
    - 一覧から RMS テンプレートを選択します。
    - [**保存**] を選択します。
    - **[OK]** をクリックします。

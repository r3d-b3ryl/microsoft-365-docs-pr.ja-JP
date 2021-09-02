---
title: Microsoft Defender for Office 365 の安全なドキュメント
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 詳細については、「セーフドキュメント」または「Microsoft 365 E5」をMicrosoft 365 E5 Security。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0ccedf53b9978329935ceb28bb0ba0695f3da67c
ms.sourcegitcommit: ef9cd046c47b340686a4f7bb123ea3b0a269769a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2021
ms.locfileid: "58863823"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 の安全なドキュメント

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セーフドキュメントは[、Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用して、保護されたビューまたは Application Guard[](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)で開いているドキュメントとファイルをスキャンして、ドキュメントをスキャンするプレミアム[機能](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)Office。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- **Office 365 セーフ SafeDocs** (または **SAFEDOCS** または **bf6f5520-59e3-4f82-974b-7dbbc4fd27c7)** サービス (サービス プランとも呼ばれる) によって制御される セーフ ドキュメントの可用性。 このサービス プランは、次のライセンス プラン (ライセンス プラン、Microsoft 365製品とも呼ばれる) で利用できます。
  - Microsoft 365 A5教員向け
  - Microsoft 365 A5学生向け
  - Microsoft 365 E5
  - Microsoft 365 E5 Security

  セーフドキュメントは、Microsoft Defender のライセンス プランOffice 365含まれていません。

  詳細については、次のトピックをご覧ください。

  - [PowerShell Microsoft 365ライセンスとサービスを表示する](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell)
  - [PowerShell Microsoft 365アカウント のライセンスとサービスの詳細を表示する](/microsoft-365/enterprise/view-account-license-and-service-details-with-microsoft-365-powershell)
  - [ライセンスの製品名とサービス プラン識別子](/azure/active-directory/enterprise-users/licensing-service-plan-reference)

- セーフドキュメントは、Microsoft 365 Apps for enterprise (以前は Office 365 ProPlus) バージョン 2004 以降でサポートされています。

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 [添付ファイル] ページに **直接移動セーフを** 使用します <https://security.microsoft.com/safeattachmentv2> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の **手順をExchange Online** 前に、アクセス許可が必要です。
  - ドキュメントのセーフ構成するには、組織の管理役割グループまたはセキュリティ管理者役割グループ **のメンバーである** 必要があります。 
  - ドキュメント設定への読み取りセーフアクセスするには、グローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー **である** 必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft はデータを処理する方法を説明します。

保護を維持するために、セーフドキュメントは分析のために[Microsoft Defender for Endpoint クラウド](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)にファイルを送信します。 Microsoft Defender for Endpoint がデータを処理する方法の詳細については [、Microsoft Defender for Endpoint データストレージとプライバシーを参照してください](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。

ドキュメントから送信セーフは、分析に必要な時間 (通常は 24 時間未満) を超えて Defender に保持されません。

## <a name="use-the-microsoft-365-defender-portal-to-configure-safe-documents"></a>[ドキュメント] Microsoft 365 Defenderを構成するには、セーフ ポータルを使用します。

1. [ポリシー] Microsoft 365 Defenderを開き、[ポリシー] セクション&の [&脅威ポリシーと添付ファイルセーフメール] に \>  \>  \> **移動** します。

2. [添付ファイル **セーフ] ページで**、[グローバル設定]**をクリックします**。

3. [グローバル **設定] が** 表示されたら、次の設定を構成します。
   - **[クライアントセーフドキュメントOffice有効** にする: トグルを右に移動して、機能を有効にします。[オンに切り替 ![ え] をオンにします ](../../media/scc-toggle-on.png) 。
   - **セーフ** ドキュメントがファイルを悪意のあるファイルと特定した場合でも、保護されたビューをクリックすることを許可する: このオプションをオフのままにすることをお勧めします (トグルは左に切り替えます。 ![ ](../../media/scc-toggle-off.png)

   完了したら、**[保存]** をクリックします。

   ![セーフ[添付ファイル] ページで [グローバル設定] を選択した後セーフ設定します。](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>PowerShell Exchange Onlineを使用してドキュメントセーフ構成する

次の構文を使用してください。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs パラメーターは_、組織全体セーフドキュメントを有効または無効にします。
- _AllowSafeDocsOpen_ パラメーターは、ドキュメントが悪意のあると識別された場合に、ユーザーが保護されたビューを離れる (つまり、ドキュメントを開く) のを許可または防止します。

この例では、セーフドキュメントの削除を有効にし、保護されたビューから悪意のあると識別されたドキュメントを開くユーザーを防止します。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

構文とパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](/powershell/module/exchange/set-atppolicyforo365)。

### <a name="configure-individual-access-to-safe-documents"></a>ドキュメントへの個別のアクセスセーフ構成する

ドキュメント機能へのアクセスを選択的に許可またはブロックするセーフ、次の手順を実行します。

1. この記事セーフ説明したように、Microsoft 365 Defenderまたは PowerShell Exchange Onlineドキュメントを有効にしてください。
2. Azure AD PowerShell を使用して、「特定のライセンス プランに対して特定の Microsoft 365 サービスを無効にする」の説明に従って、特定のユーザーの セーフ ドキュメントを[無効にします](/microsoft-365/enterprise/disable-access-to-services-with-microsoft-365-powershell#disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan)。

  PowerShell で無効にするサービス プランの名前は **SAFEDOCS です**。

詳細については、次のトピックをご覧ください。

- [PowerShell Microsoft 365ライセンスとサービスを表示する](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell)
- [PowerShell Microsoft 365アカウント のライセンスとサービスの詳細を表示する](/microsoft-365/enterprise/view-account-license-and-service-details-with-microsoft-365-powershell)
- [ライセンスの製品名とサービス プラン識別子](/azure/active-directory/enterprise-users/licensing-service-plan-reference)

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>Microsoft Defender for Endpoint Service にオンボードして監査機能を有効にする

Microsoft Defender for Endpoint を展開するには、展開のさまざまなフェーズを実行する必要があります。 オンボーディングの後、監査機能をポータルで構成Microsoft 365 Defenderできます。

詳細については [、「Onboard to the Microsoft Defender for Endpoint service」を参照してください](/microsoft-365/security/defender-endpoint/onboarding)。 その他のヘルプが必要な場合は、「Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング [」を参照してください](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)。

### <a name="how-do-i-know-this-worked"></a>設定が適用されたことを確認する方法

ドキュメントを有効にし、構成セーフするには、次の手順を実行します。

- Microsoft 365 Defender ポータルで、[ポリシー] セクションの[& Collaboration \> **Policies & Rules** Threat \> **Policies** セーフ \> **Attachments]** に移動し \> **、[Office** クライアントの セーフ ドキュメントを有効にする] と [セーフ ドキュメントがファイルを悪意のある設定として識別した場合でも、保護されたビューをクリックするユーザーを許可する] を確認します。

- PowerShell で次のコマンドをExchange Onlineし、プロパティの値を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- ドキュメント保護をテストするには、次セーフ使用できます。 これらのドキュメントは、マルウェア対策EICAR.TXTウイルス対策ソリューションをテストするファイルと似ています。 ファイルは有害ではないが、ドキュメント保護セーフトリガーします。

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)

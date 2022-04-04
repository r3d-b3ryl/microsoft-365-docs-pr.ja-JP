---
title: Microsoft Defender for Office 365 の安全なドキュメント
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 詳細については、「セーフ/A5 または Microsoft 365 E5/A5 セキュリティMicrosoft 365 E5ドキュメント」を参照してください。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab5e35954cac20a18e34f418b5b9fcdc7f2fd007
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466347"
---
# <a name="safe-documents-in-microsoft-365-e5a5"></a>セーフ/A5 のMicrosoft 365 E5ドキュメント

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セーフドキュメントは、[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) のクラウド バックエンドを使用して、保護されたビューまたはアプリケーション ガードで開いている Office ドキュメントをスキャンするプレミアム[機能](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)Office。[](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

ユーザーは、ローカル デバイスに Defender for Endpoint をインストールして、ドキュメント保護セーフ必要とされません。 次の要件セーフ満たされている場合、ユーザーはドキュメント保護を受け取る必要があります。

- セーフの説明に従って、組織でドキュメントが有効になります。
- 必要なライセンスプランのライセンスがユーザーに割り当てられます。 セーフ ドキュメントは **、Office 365 SafeDocs** (または **SAFEDOCS** または **bf6f5520-59e3-4f82-974b-7dbbc4fd27c7**) サービス プラン (サービスとも呼ばれる) によって制御されます。 このサービス プランは、次のライセンス プラン (ライセンス プラン、Microsoft 365製品とも呼ばれる) で利用できます。
  - Microsoft 365 A5教員向け
  - Microsoft 365 A5学生向け
  - Microsoft 365 E5
  - Microsoft 365 E5 Security

  セーフドキュメントは、Microsoft Defender のライセンス プランOffice 365含まれていません。

  詳細については、「ライセンスの [製品名とサービス プラン識別子」を参照してください](/azure/active-directory/enterprise-users/licensing-service-plan-reference)。

- 2004 以降Microsoft 365 Apps for enterprise (以前は Office 365 ProPlus) バージョンを使用しています。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の **手順をExchange Online** 前に、アクセス許可が必要です。
  - ドキュメントのセーフ構成するには、組織の管理またはセキュリティ管理者の役割グループ **のメンバーである** 必要があります。
  - ドキュメント設定への読み取りセーフアクセスするには、グローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー  **である** 必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft はデータを処理する方法を説明します。

保護を維持するために、セーフドキュメントは分析のために [Microsoft Defender for Endpoint クラウド](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)にファイルを送信します。 Microsoft Defender for Endpoint がデータを処理する方法の詳細については、「 [Microsoft Defender for Endpoint data storage and privacy」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。

セーフドキュメントによって送信されたファイルは、分析に必要な時間 (通常は 24 時間未満) を超えて Defender for Endpoint に保持されません。

## <a name="use-the-microsoft-365-defender-portal-to-configure-safe-documents"></a>Microsoft 365 Defender ポータルを使用してドキュメントセーフ構成する

1. [Microsoft 365 Defenderポータル \>  \>  \> <https://security.microsoft.com>で、[ポリシー] セクション&の [&脅威ポリシーと添付ファイルセーフメールを送信する] **に移動** します。 **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

2. **[安全な添付ファイル]** ページで **[グローバル設定]** をクリックします。

3. [グローバル **設定] が** 表示されたら、次の設定を構成します。
   - **[クライアントセーフドキュメント** Officeオンにする: トグルを右に移動して機能を![有効にします。[オンに切り替え]をオンにします](../../media/scc-toggle-on.png)。
   - **セーフ Documents** がファイルを悪意のあると特定した場合でも、保護されたビューをクリックすることを許可する: このオプションはオフのままにすることをお勧めします (![](../../media/scc-toggle-off.png)トグルは左に切り替えます。

   完了したら、**[保存]** をクリックします。

   :::image type="content" source="../../media/safe-docs-global-settings.png" alt-text="[セーフ添付ファイル] ページで [グローバル設定] を選択した後の [ドキュメントの設定セーフ設定]" lightbox="../../media/safe-docs-global-settings.png":::

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>PowerShell Exchange Onlineを使用してドキュメントセーフ構成する

ユーザーの PowerShell でドキュメントを構成セーフする場合は、PowerShell で次Exchange Onlineします。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs パラメーターは_、組織全体セーフドキュメントを有効または無効にします。
- _AllowSafeDocsOpen_ パラメーターは、ドキュメントが悪意のあると識別された場合に、ユーザーが保護されたビューを離れる (つまり、ドキュメントを開く) のを許可または防止します。

この例では、セーフドキュメントの削除を有効にし、保護されたビューから悪意のあると識別されたドキュメントを開くユーザーを防止します。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

構文とパラメーターの詳細については、「 [Set-AtpPolicyForO365」を参照してください](/powershell/module/exchange/set-atppolicyforo365)。

### <a name="configure-individual-access-to-safe-documents"></a>ドキュメントへの個々のアクセスセーフ構成する

ドキュメント機能へのアクセスを選択的に許可またはブロックするセーフ、次の手順を実行します。

1. この記事セーフ説明したように、Microsoft 365 Defenderまたは PowerShell Exchange Onlineドキュメントを有効にする。
2. PowerShell Azure ADを使用して、特定のセーフの特定のユーザーに対して特定の Microsoft 365 サービスを無効にする」の説明に従って、セーフ ドキュメントを[無効にします](/microsoft-365/enterprise/disable-access-to-services-with-microsoft-365-powershell#disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan)。

  PowerShell で無効にするサービス プランの名前は **SAFEDOCS です**。

詳細については、次のトピックをご覧ください。

- [PowerShell Microsoft 365ライセンスとサービスを表示する](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell)
- [PowerShell Microsoft 365アカウント のライセンスとサービスの詳細を表示する](/microsoft-365/enterprise/view-account-license-and-service-details-with-microsoft-365-powershell)
- [ライセンスのための製品名とサービス プラン識別子](/azure/active-directory/enterprise-users/licensing-service-plan-reference)

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>監査機能を有効にする Microsoft Defender for Endpoint サービスにオンボードする

監査機能を有効にするには、ローカル デバイスに Microsoft Defender for Endpoint がインストールされている必要があります。 Microsoft Defender for Endpoint を展開するには、展開のさまざまなフェーズを実行する必要があります。 オンボーディングの後、監査機能をポータルで構成Microsoft 365 Defenderできます。

詳細については、「 [Onboard to the Microsoft Defender for Endpoint service」を参照してください](/microsoft-365/security/defender-endpoint/onboarding)。 その他のヘルプが必要な場合は、「 [Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング」を参照してください](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)。

### <a name="how-do-i-know-this-worked"></a>設定が適用されたことを確認する方法

ドキュメントを有効にし、構成セーフするには、次の手順を実行します。

- Microsoft 365 Defender  \> ポータルで、[ポリシー] セクションの [& コラボレーション ポリシー **& ルール** \>  \>の脅威ポリシー **セーフ**  \> 添付ファイルの電子メール] セクションの [グローバル設定] に移動し、Office クライアントの [セーフ ドキュメントを有効にする] **を確認****します。[ドキュメント] でファイルが** 悪意のある設定としてセーフ場合でも、保護されたビューをクリックできます。

- PowerShell で次のコマンドを実行Exchange Onlineプロパティの値を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- ドキュメント保護のテストには、次セーフ使用できます。 これらのファイルは、マルウェア対策EICAR.TXTウイルス対策ソリューションをテストするファイルと似ています。 ファイルは有害ではないが、ドキュメント保護セーフトリガーします。

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)

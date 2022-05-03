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
description: Microsoft 365 E5/A5 または Microsoft 365 E5/A5 セキュリティのドキュメントセーフについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3fa1c7e07c1e1cd117ee20f4712dbbadad3c2b5c
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2022
ms.locfileid: "65174145"
---
# <a name="safe-documents-in-microsoft-365-e5a5"></a>Microsoft 365 E5/A5 でドキュメントをセーフする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セーフ ドキュメントは、[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)のクラウド バックエンドを使用して[、保護されたビュー](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)または Application Guard で開かれたOfficeドキュメントを[スキャンしてOfficeする](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)プレミアム機能です。

ユーザーは、ドキュメント保護をセーフするために、ローカル デバイスに Defender for Endpoint をインストールする必要はありません。 次のすべての要件が満たされている場合、ユーザーはドキュメント保護セーフ取得します。

- セーフ ドキュメントは、この記事の説明に従って組織内で有効になっています。
- 必要なライセンス プランのライセンスがユーザーに割り当てられます。 セーフドキュメントは **、Office 365 SafeDocs** (または **SAFEDOCS** または **bf6f5520-59e3-4f82-974b-7dbbc4fd27c7**) サービス プラン (サービスとも呼ばれます) によって制御されます。 このサービス プランは、次のライセンス プラン (ライセンス プラン、Microsoft 365 プラン、製品とも呼ばれます) で利用できます。
  - 教職員向けのMicrosoft 365 A5
  - 学生向けのMicrosoft 365 A5
  - Microsoft 365 E5 Security

  セーフ ドキュメントは、Microsoft Defender for Office 365 ライセンス プランには含まれません。

  詳細については、ライセンスの [製品名とサービス プラン識別子に関するページを](/azure/active-directory/enterprise-users/licensing-service-plan-reference)参照してください。

- Microsoft 365 Apps for enterprise (以前は Office 365 ProPlus と呼ばられていました) バージョン 2004 以降を使用しています。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行するには **、Exchange Online** でアクセス許可が必要です。
  - セーフドキュメント設定を構成するには、**組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。
  - セーフドキュメントの設定に対する読み取り専用アクセス権を持つ場合は、**グローバル 閲覧者** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft はデータをどのように処理しますか?

保護を維持するために、セーフ ドキュメントは分析のために[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) クラウドにファイルを送信します。 Microsoft Defender for Endpointがデータを処理する方法の詳細については、データ[ストレージとプライバシー Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)を参照してください。

セーフ ドキュメントによって送信されたファイルは、分析に必要な時間 (通常は 24 時間以内) を超えて Defender for Endpoint に保持されません。

## <a name="use-the-microsoft-365-defender-portal-to-configure-safe-documents"></a>Microsoft 365 Defender ポータルを使用してセーフドキュメントを構成する

1. Microsoft 365 Defender ポータルの [ポリシー] **セクション****の** <https://security.microsoft.com>[電子メール & コラボレーション \> **ポリシー&ルール** \> **の脅威ポリシー** \> **セーフ添付ファイル**] に移動します。 **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

2. **[安全な添付ファイル]** ページで **[グローバル設定]** をクリックします。

3. 表示される **[グローバル設定]** ポップアップで、次の設定を構成します。
   - **Office クライアントのドキュメントのセーフを有効にする**:トグルを右に移動して、機能をオンにします。![トグル オンです](../../media/scc-toggle-on.png)。
   - **ドキュメントセーフファイルが悪意のあるものとして識別された場合でも、ユーザーが保護されたビューをクリック** できるようにします。このオプションはオフのままにすることをお勧めします (トグルは左に切り替えます](../../media/scc-toggle-off.png)。 ![

   完了したら、**[保存]** をクリックします。

   :::image type="content" source="../../media/safe-docs-global-settings.png" alt-text="[セーフ添付ファイル] ページで [グローバル設定] を選択した後の [セーフ ドキュメントの設定]" lightbox="../../media/safe-docs-global-settings.png":::

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>PowerShell Exchange Onlineを使用してセーフドキュメントを構成する

PowerShell を使用してドキュメントセーフ構成する場合は、powerShell Exchange Onlineで次の構文を使用します。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_ パラメーターは、組織全体のドキュメントセーフ有効または無効にします。
- _AllowSafeDocsOpen_ パラメーターを使用すると、ドキュメントが悪意のあるユーザーとして識別された場合に、ユーザーが保護されたビューを離れる (つまりドキュメントを開く) ことを許可または禁止できます。

この例では、組織全体に対してドキュメントのセーフを有効にし、ユーザーが保護されたビューから悪意のあると識別されたドキュメントを開くのを防ぎます。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

構文とパラメーターの詳細については、「 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)」を参照してください。

### <a name="configure-individual-access-to-safe-documents"></a>セーフ ドキュメントへの個々のアクセスを構成する

セーフ ドキュメント機能へのアクセスを選択的に許可またはブロックする場合は、次の手順に従います。

1. この記事で前述したように、Microsoft 365 Defender ポータルでドキュメントセーフを有効にするか、PowerShell をExchange Onlineします。
2. Azure AD PowerShell を使用して、特定のユーザーのセーフドキュメントを無効にします。「特定の[ライセンス プランの特定のユーザーに対して特定のMicrosoft 365 サービスを無効にする」を](/microsoft-365/enterprise/disable-access-to-services-with-microsoft-365-powershell#disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan)参照してください。

  PowerShell で無効にするサービス プランの名前は **SAFEDOCS** です。

詳細については、次のトピックをご覧ください。

- [PowerShell を使用してMicrosoft 365ライセンスとサービスを表示する](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell)
- [PowerShell を使用Microsoft 365アカウント ライセンスとサービスの詳細を表示する](/microsoft-365/enterprise/view-account-license-and-service-details-with-microsoft-365-powershell)
- [ライセンスのための製品名とサービス プラン識別子](/azure/active-directory/enterprise-users/licensing-service-plan-reference)

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>Microsoft Defender for Endpoint サービスにオンボードして監査機能を有効にする

監査機能を有効にするには、ローカル デバイスにMicrosoft Defender for Endpointがインストールされている必要があります。 Microsoft Defender for Endpointをデプロイするには、デプロイのさまざまなフェーズを実行する必要があります。 オンボード後、Microsoft 365 Defender ポータルで監査機能を構成できます。

詳細については、「[Microsoft Defender for Endpoint サービスへのオンボード](/microsoft-365/security/defender-endpoint/onboarding)」を参照してください。 追加のヘルプが必要な場合は、「[Microsoft Defender for Endpointオンボードの問題のトラブルシューティング](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)」を参照してください。

### <a name="how-do-i-know-this-worked"></a>設定が適用されたことを確認する方法

ドキュメントセーフ有効にし、構成したことを確認するには、次のいずれかの手順を実行します。

- Microsoft 365 Defender ポータルで、[ポリシー **] セクション** の [添付ファイル] の **[メール & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** \> **セーフ添付ファイル****]** に\>移動し、**Office クライアント** と **セーフドキュメントを有効にするセーフドキュメントでファイルが悪意のある設定として識別された場合でも、ユーザーが保護されたビューをクリック** できるようにします。

- PowerShell で次のコマンドExchange Online実行し、プロパティ値を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- ドキュメント保護セーフテストするには、次のファイルを使用できます。 これらのファイルは、マルウェア対策ソリューションとウイルス対策ソリューションをテストするためのEICAR.TXT ファイルに似ています。 ファイルは有害ではありませんが、ドキュメント保護セーフトリガーされます。

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)

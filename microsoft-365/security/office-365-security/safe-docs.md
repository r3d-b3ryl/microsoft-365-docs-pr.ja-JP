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
description: Microsoft 365 E5 または Microsoft 365 E5 セキュリティの安全なドキュメントについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 75dfa9e5687a4c4b561067190e7ce338074b2f66
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407422"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 の安全なドキュメント

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

安全なドキュメントは、Microsoft 365 E5 または Microsoft 365 E5 セキュリティの機能で[、Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)を使用して、保護ビューで開いているドキュメントとファイルをスキャンします。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- 安全なドキュメントは *、Microsoft 365 E5* または *Microsoft 365 E5 セキュリティ* ライセンスを持つユーザーにのみ使用できます。 これらのライセンスは、Microsoft Defender の 365 プランOffice含まれていません。

- 安全なドキュメントは、Microsoft 365 Apps for enterprise (以前は Office 365 ProPlus) バージョン 2004 以降でサポートされています。

- <https://protection.office.com> でセキュリティ/コンプライアンス センターを開きます。 ATP の [安全な添付ファイル] ページ **に直接移動するには** 、 を開きます <https://protection.office.com/safeattachmentv2> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行するには **、Exchange Online** でアクセス許可を割り当てる必要があります。
  - 安全なドキュメント設定を構成するには、組織の管理またはセキュリティ管理者の役割グループの **メンバーである** 必要があります。
  - 安全なドキュメント設定への読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループのメンバー **である** 必要があります。

  詳細については、「[Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)」を参照してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 の他の機能に必要なアクセス許可とアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  >
  > - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft はデータを処理する方法を説明します。

保護を維持するために、セーフ ドキュメントは分析のために [Microsoft Defender for Endpoint クラウド](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) にファイルを送信します。 Microsoft Defender for Endpoint がデータを処理する方法の詳細については [、Microsoft Defender for Endpoint データストレージとプライバシーを参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。

安全なドキュメントによって送信されたファイルは、分析に必要な時間を超えて Defender に保持されません (通常、24 時間未満)。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>セキュリティ コンプライアンス センター&使用して安全なドキュメントを構成する

1. セキュリティ セキュリティ コンプライアンス センター&に移動し、[**脅威管理ポリシー** ATP の安全な添付ファイル] に移動し、[ \>  \> グローバル設定]**をクリックします**。

2. [グローバル **設定] が** 表示されたら、次の設定を構成します。

   - **[クライアントの安全な** ドキュメントOfficeする: トグルを右に移動して機能を有効にする: ![ トグルをオンにします ](../../media/scc-toggle-on.png) 。

   - **安全なドキュメント** でファイルが悪意のあるファイルとして識別された場合でも、保護されたビューをクリックすることを許可する: このオプションをオフのままにすることをお勧めします (トグルは左 ![ に切り替えます。 ](../../media/scc-toggle-off.png)

   完了したら、**[保存]** をクリックします。

   ![[安全な添付ファイル] ページで [グローバル設定] を選択した後の安全なドキュメントの設定。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell を使用して安全なドキュメントを構成する

次の構文を使用してください。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs パラメーター_ は、組織全体の安全なドキュメントを有効または無効にします。
- _AllowSafeDocsOpen_ パラメーターは、ドキュメントが悪意のあると識別された場合に、ユーザーが保護されたビューを離れる (つまり、ドキュメントを開く) のを許可または防止します。

この例では、組織全体で安全なドキュメントを有効にし、ユーザーが保護されたビューから悪意のあると識別されたドキュメントを開くのを防ぐ。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

構文とパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。

### <a name="how-do-i-know-this-worked"></a>設定が適用されたことを確認する方法

セーフ ドキュメントを有効にし、構成したことを確認するには、次の手順を実行します。

- セキュリティ & コンプライアンス センターで、[脅威管理ポリシー ATP の安全な添付ファイル] に移動し、[グローバル設定] をクリックし \>  \> **、[Office** クライアントの安全なドキュメントを有効にする] と [安全なドキュメントが悪意のある設定としてファイルを識別した場合でも、保護されたビューをクリックするユーザーを許可する] を確認します。

- Exchange Online PowerShell で次のコマンドを実行し、プロパティの値を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 安全なドキュメント保護をテストするには、次のファイルを使用できます。 これらのドキュメントは、マルウェア対策EICAR.TXTウイルス対策ソリューションをテストするファイルと似ています。 ファイルは有害ではないが、安全なドキュメント保護をトリガーします。

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)

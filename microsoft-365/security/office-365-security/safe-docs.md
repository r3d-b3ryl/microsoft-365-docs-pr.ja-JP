---
title: Microsoft Defender for Office 365 の安全なドキュメント
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Microsoft 365 E5 または Microsoft 365 E5 セキュリティの安全なドキュメントについて説明します。
ms.openlocfilehash: 1bf802422dc05babaf5e2616468f8326b7007dc8
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682939"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 の安全なドキュメント

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


安全なドキュメントは、Microsoft 365 E5 または Microsoft 365 E5 セキュリティの機能で[、Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用して、保護ビューで開いているドキュメントやファイルをスキャン[します。](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- 安全なドキュメントは *、Microsoft 365 E5* または *Microsoft 365 E5 セキュリティ* ライセンスを持つユーザーだけが利用できます。 これらのライセンスは、Office 365 プランの Microsoft Defender には含まれていません。

- 安全なドキュメントは、Microsoft 365 Apps for enterprise (以前の Office 365 ProPlus) バージョン 2004 以降でサポートされています。

- <https://protection.office.com> でセキュリティ/コンプライアンス センターを開きます。 [ATP の安全な添付ファイル **] ページに直接移動するには** 、開きます <https://protection.office.com/safeattachmentv2> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。
  - 安全なドキュメントの設定を構成するには、組織の管理役割グループまたはセキュリティ管理者役割グループの **メンバーである** 必要があります。
  - 安全なドキュメントの設定に読み取り専用でアクセスするには、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である** 必要があります。

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft はデータを処理する方法を説明します。

保護された状態を維持するために、安全なドキュメントは分析のために [Microsoft Defender for Endpoint クラウド](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) にファイルを送信します。 Microsoft Defender for Endpoint がデータを処理する方法の詳細については、Microsoft Defender for Endpoint のデータストレージとプライバシーに関するページ [をご覧ください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。

安全なドキュメントによって送信されたファイルは、分析に必要な時間を超えて Defender に保持されません (通常、24 時間未満)。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>セキュリティ/コンプライアンス センター&使用して安全なドキュメントを構成する

1. セキュリティ/コンプライアンス センター&、**脅威管理** ポリシー ATP の安全な添付ファイルに移動し、[グローバル設定] \>  \> を **クリックします**。

2. 表示される **グローバル設定** のフライアウトで、次の設定を構成します。

   - **[安全な** ドキュメント] を Officeクライアントに対して有効にする: トグルを右に移動して機能を有効にします。オンに切り ![ 替えます ](../../media/scc-toggle-on.png) 。

   - **安全な** ドキュメントでファイルが悪意のあるものとして識別された場合でも、保護ビューをクリックすることを許可します。このオプションはオフのままにすることをお勧めします (左側のトグルをオフのままに ![ します ](../../media/scc-toggle-off.png) )。

   完了したら、**[保存]** をクリックします。

   ![[安全な添付ファイル] ページで [グローバル設定] を選択した後の安全なドキュメントの設定。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell を使用して安全なドキュメントを構成する

次の構文を使用してください。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs パラメーターは_、組織全体の安全なドキュメントを有効または無効にします。
- _AllowSafeDocsOpen_ パラメーターは、ドキュメントが悪意のあるものとして識別された場合に、ユーザーが保護ビューを離れる (つまり、ドキュメントを開く) のを許可または防止します。

この例では、組織全体に対して安全なドキュメントを有効にし、悪意のあるドキュメントとして識別されたドキュメントを保護ビューからユーザーが開くのを防止します。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

構文およびパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)してください。

### <a name="how-do-i-know-this-worked"></a>設定が適用されたことを確認する方法

安全なドキュメントを有効にし、構成されていることを確認するには、次の手順を実行します。

- セキュリティ & コンプライアンス センターで、脅威管理ポリシー ATP の安全な添付ファイルに移動し、[グローバル設定] をクリックして \>  \> **、Office** クライアントの安全なドキュメントを有効にし、安全なドキュメントでファイルが悪意のある設定として識別された場合でも、保護ビューをクリックできるユーザーを許可します。

- Exchange Online PowerShell で次のコマンドを実行し、プロパティの値を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 安全なドキュメント保護をテストするには、次のファイルを使用できます。 これらのドキュメントは、マルウェア対策EICAR.TXTウイルス対策ソリューションをテストする目的で使用されるファイルと似ています。 ファイルは有害ではないが、安全なドキュメント保護をトリガーします。

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)

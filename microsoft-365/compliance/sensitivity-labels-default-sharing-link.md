---
title: 秘密度ラベルを使用して既定の共有リンクの種類を構成する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 秘密度ラベルを使用して、SharePoint と OneDrive のサイトと個ドキュメントの既定の共有リンクの種類を構成します。
ms.openlocfilehash: 132a526cc591f34722e4c0e8d4982859790558da
ms.sourcegitcommit: 5c64002236561000c5bd63c71423e8099e803c2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2022
ms.locfileid: "65286892"
---
# <a name="use-sensitivity-labels-to-configure-the-default-sharing-link-type-for-sites-and-documents-in-sharepoint-and-onedrive"></a>秘密度ラベルを使用して、SharePoint と OneDrive のサイトと個ドキュメントの既定の共有リンクの種類を構成する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview コンプライアンス ポータルに表示される[秘密度ラベル](sensitivity-labels.md)の設定に対する追加構成として、これらのラベルは、SharePoint サイトまたは OneDrive アカウントと、個々のドキュメントに対応する既定の共有リンクの種類の設定を構成するために使用できます。 これらの設定は自動的に選択されますが、Office アプリで **[共有]** ボタンを選択したユーザーにはあまり表示されません。 次に例を示します。

![[既定の共有リンク] ダイアログ ボックスの例。](../media/default-sharing-link-example.png)

既定の共有リンク タイプは、ユーザーがファイルとフォルダーを共有するときに自動的に選択される範囲 (対象者) とアクセス許可 (表示または編集) を設定します。 ユーザーは共有リンクを送信する前にこれらの既定設定をいつでも上書きできますが、選択した設定は安全なベースラインを提供します。 通常、ユーザーは共有する前に設定を変更しません。

サイト レベル (SharePoint サイトまたは OneDrive アカウント) では、秘密度ラベルは、SharePoint 管理センターのサイトに構成できる既定の共有リンクの種類を設定するための便利な代替手段を提供します。 詳細については、SharePoint のドキュメントから「[ サイトの既定のリンクの種類を変更する](/sharepoint/change-default-sharing-link)」を参照してください。

このサイト レベルの構成は、すべてのドキュメントの秘密度が同じレベルになっている SharePoint サイトでは適切に機能します。ただし、秘密度のレベルが高く、より制限的な設定が必要なドキュメントがサイトに含まれている場合は、既定の共有リンクの種類に異なる設定の秘密度ラベルを構成して、そのラベルをドキュメントに適用できます。

このシナリオのように、サイトに既定のリンクの種類が設定されていて、そのサイト内のドキュメントに別の既定の共有リンクの種類が設定されている場合は、そのドキュメントの共有オプションをユーザーが選択するときに、より制限の厳しい範囲設定が適用されます。次に例を示します。

- 既定の共有リンクの種類は、組織内のすべてのユーザーを対象としています。 そのサイト内のドキュメントには、既定の共有リンクの種類が特定のユーザーに設定されたラベルが付けされます。 ユーザーがそのドキュメントを共有すると、選択された既定の共有リンクの種類が特定のユーザーを対象にします。

- サイトの既定の共有リンクの種類は、編集権限を持つ特定のユーザーを対象とします。 そのサイトのドキュメントには、組織内のすべてのユーザーに設定された既定の共有リンクの種類が表示され、表示権限が付与されます。 ユーザーがそのドキュメントを共有すると、選択された既定の共有リンクの種類は、編集権限を持特定のユーザーを対象とします。

ドキュメントの既定のリンクの種類を構成することも、サイトレベルの設定なしで適切な場合があります。 たとえば、SharePoint サイトは通常、同じ種類のドキュメントをホストするように編成されていますが、OneDrive アカウントの場合はそうではありません。 ユーザーは通常、さまざまなファイルを OneDrive に保存します。これには、多くの場合、個人用ドキュメントとビジネス用ドキュメントが混在しています。 ユーザーの OneDriveア カウントのすべてのドキュメントに既定のリンクの種類を設定することは実用的ではないと思われますが、個々のドキュメントはこれらの設定の恩恵を受けることができます。 例:

- **[非常に機密性の高い社外秘]** というラベルの付いたドキュメントには、組織内の誰よりも特定の人に共有を制限する既定の共有リンクの種類があります。
- **[全般]** というラベルの付いたドキュメントには、組織内のユーザーへの共有を制限する既定の共有リンクの種類があります。
- **[個人用]** というラベルの付いたドキュメントには、既定の共有リンクの種類が設定され、リンクを持つすべてのユーザーと共有できます。

## <a name="prerequisites"></a>前提条件

サイトに既定の共有リンクの種類を適用するには、コンテナに対して秘密度ラベルを有効にする必要があります。 テナントでこの機能がまだ有効になっていない場合は、「[コンテナーの感度ラベルを有効にしてラベルを同期する方法](sensitivity-labels-teams-groups-sites.md#how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels)」を参照してください。

SharePoint および OneDrive のドキュメントに既定の共有リンクの種類を適用するには、これらのサービスで秘密度ラベルを有効にする必要があります。 テナントでこの機能がまだ有効になっていない場合は、「[SharePoint と OneDrive 用の秘密度ラベルの有効化](sensitivity-labels-sharepoint-onedrive-files.md#how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in) (オプトイン)」を参照してください。

PowerShel lセッションでは、「[Office 365 セキュリティ/コンプライアンス センター PowerShell への接続](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を行って、既定の共有リンクの種類の設定を構成する必要があります。

> [!NOTE]
> 必須ではありませんが、最初に [Microsoft Purview コンプライアンス ポータルで秘密度ラベルの作成と構成を実行して](create-sensitivity-labels.md)、既定の共有リンクの種類を構成する設定で、これらのラベルを変更することが最も簡単です。

## <a name="how-to-configure-settings-for-the-default-sharing-link-type"></a>既定の共有リンクの種類の設定を構成する方法

既定の共有リンクの種類の構成設定では、以下のように、PowerShell *AdvancedSettings* パラメーターを、[セキュリティ センターとコンプライアンス センターの PowerShell](/powershell/exchange/scc-powershell) の [Set-Label](/powershell/module/exchange/set-label) および [New-Label](/powershell/module/exchange/new-labelpolicy) コマンドレットとともに使用します。

- **DefaultSharingScope**: 使用可能な値は次のとおりです。
    - **SpecificPeople**: サイトの既定の共有リンクを "特定のユーザー" リンクに設定します。
    - **Organization**: サイトの既定の共有リンクを "組織" リンクまたは会社共有可能リンクに設定します。
    - **Anyone**: サイトの既定の共有リンクを匿名アクセスまたは [すべてのユーザー] リンクに設定します。

- **DefaultShareLinkPermission**: 使用可能な値は次のとおりです。
    - **View**: サイトの既定のリンクアクセス許可を "表示" アクセス許可に設定します。
    - **Edit**: サイトの既定のリンクアクセス許可を "編集" アクセス許可に設定します。

これら 2 つの設定と値は、*DefaultSharingScope*、*DefaultShareLinkPermission* および [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) コマンドレットのパラメーターと同等です。

PowerShell の例、秘密度ラベル GUID は **8faca7b8-8d20-48a3-8ea2-0f96310a848e** です:

- 既定の共有リンクの種類を SpecificPeople に設定するには、以下の手順を踏みます。
    
    ````powershell
    Set-Label -Identity 8faca7b8-8d20-48a3-8ea2-0f96310a848e -AdvancedSettings @{DefaultSharingScope="SpecificPeople"}
    ````

- 既定の共有リンクの種類のアクセス許可を [編集] に設定するには、以下の手順を踏みます。
    
    ````powershell
    Set-Label -Identity 8faca7b8-8d20-48a3-8ea2-0f96310a848e -AdvancedSettings @{DefaultShareLinkPermission="Edit"}
    ````

サイトの既定の共有リンクの種類の設定を構成するには、Microsoft Purview コンプライアンス ポータルで秘密度ラベルを作成するときに、[秘密度ラベルの範囲](sensitivity-labels.md#label-scopes)に **[グループとサイト]** を含める必要があります。 作成後、**[ラベル]** ページの **[範囲]** 列に **サイト、UnifiedGroup** として表示され、PowerShell *ContentType* 設定にも同じ値が表示されます。 ドキュメントの場合、範囲には **[ファイルとメール]** が含まれている必要があります。これらは **[ファイル、メール]** として表示されます。 その後で以下の手順に従います。

- 範囲に **[グループとサイト]** が含まれている場合、そのサイトのデフォルトの共有リンクタイプを設定するラベルをサイトに適用できます。 サイトに秘密度ラベルを適用する方法については、「[コンテナーに秘密度ラベルを適用する](sensitivity-labels-teams-groups-sites.md#how-to-apply-sensitivity-labels-to-containers)」を参照してください。

- 秘密度ラベルの範囲に **[ファイルとメール]** が含まれている場合、そのラベルをドキュメントに適用できます。これにより、そのドキュメントの既定の共有リンクの種類が設定されます。ラベルは [手動](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)で適用することも、[自動的](apply-sensitivity-label-automatically.md)に適用することもできます。

> [!TIP]
> [ラベル ポリシー設定](sensitivity-labels.md#what-label-policies-can-do)として、ラベルが新しいサイトまたは新しいドキュメントに適用されるデフォルトの秘密度ラベルであることを指定することもできます。

### <a name="powershell-tips-for-specifying-the-advanced-settings"></a>詳細設定を指定するための PowerShell のヒント

秘密度ラベルは名前で指定できますが、ラベル名または表示名を指定する際の混乱を避けるために、ラベル GUID を使用することをお勧めします。GUID を見つけて、ラベルの範囲を確認するには、以下の手順に従います。

````powershell
Get-Label | Format-Table -Property DisplayName, Name, Guid, ContentType
````

これらの詳細設定のいずれかを秘密度ラベルから削除するには、同じ AdvancedSettings パラメーター構文を使用しますが、null 文字列値を指定します。 例として、以下のようなものがあります:

````powershell
Set-Label -Identity 8faca7b8-8d20-48a3-8ea2-0f96310a848e -AdvancedSettings @{DefaultSharingScope=""}
````


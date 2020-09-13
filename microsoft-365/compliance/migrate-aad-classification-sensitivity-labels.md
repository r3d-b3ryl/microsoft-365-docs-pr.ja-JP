---
title: Microsoft 365 グループの Azure Active Directory 分類と機密ラベル
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
description: この記事では、従来の Azure Active Directory 分類と機密ラベルについて説明します。
ms.openlocfilehash: 2506e7f467a485878f1e26a23ee1071907b41614
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545661"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Microsoft 365 グループの Azure Active Directory 分類と機密ラベル

この記事では、従来の Azure Active Directory 分類と機密ラベルについて説明します。

[これらのサービス](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#support-for-the-sensitivity-labels)では、機密ラベルがサポートされています。

機密ラベルの詳細については、「 [機密ラベルに](sensitivity-labels.md)ついて」を参照してください。

サイトおよび Microsoft 365 グループの機密ラベルとその動作の詳細については、「 [Microsoft Teams、microsoft 365 グループ、および SharePoint サイトのコンテンツを保護するための機密情報を使用する](sensitivity-labels-teams-groups-sites.md)」を参照してください。

従来の AAD 分類から機密ラベルに移行する場合のベストプラクティスについては、次のシナリオを参照してください。

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>シナリオ 1: テナントは、ドキュメントと電子メールの従来の AAD 分類または機密ラベルを使用していません

- テナント管理者は、AAD powershell コマンドレットを使用してテナントフラグ "EnableMIPLabels" を true に設定することにより、グループの機密ラベルを有効にします。
- テナント管理者は、 [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で機密ラベルを作成します。
    - テナント管理者は、暗号化やウォーターマークなどのファイルおよび電子メール関連のアクションを選択できます。
    - テナント管理者は、機密ラベルに対して Microsoft 365 グループと SharePoint Online のサイト関連アクションを選択できます。
- テナント管理者がポリシーを発行します。
- **互換性のあるワークロード** 機密ラベルを表示します。 機密ラベルを使用してグループを作成します。 互換性のあるワークロードは、機密ラベルをサポートするサービスです。
- **互換性のないワークロード** は、機密ラベルがまだサポートされていないサービスです。 ただし、グループを作成することはできますが、互換性のないワークロードを使用して機密ラベルに関連付けることはできません。 このようなグループを機密ラベルと関連付けるには、テナント管理者は PowerShell コマンドレットを実行できます。

表 1. 互換性があり、互換性のないワークロードの動作–グループを作成、編集、または削除する

|ワークロード|グループウィンドウでユーザーに表示されるラベルの一覧|新しいグループを作成する |グループの編集 |Delete group |
|:-------|:-------|:--------|:--------|:--------|   
|動作   |機密ラベル |動作に変更はありません。 |動作に変更はありません。 |動作に変更はありません。 |
|互換性のない |機密ラベルは表示されません。 |ユーザーは、機密ラベルを選択せずにグループを作成できます。 <br><br> 注: 管理者はコマンドレットを実行して、バックグラウンドで機密ラベルを適用できます。 |**ケース 1**: 以前に選択した機密ラベルがありません。 ユーザーはグループを編集できます。<br><br> **ケース 2**: コマンドレットを使用して、バックグラウンドで以前に適用された機密ラベル ユーザーは、グループを正常に編集できます。ユーザーがラベルに関して、プライバシー設定の無効な組み合わせを選択するケースは除きます。 |動作に変更はありません。|

> [!NOTE]
> Outlook デスクトップクライアント (Win 32) の場合、管理者がテナントで機密ラベルを有効にし、ユーザーが以前のバージョンの Outlook デスクトップクライアント (Win 32) を使用しています。
>
> - ユーザーには、Outlook デスクトップクライアントの古いバージョンに機密ラベルが表示されます。
> - ただし、ユーザーがグループを編集して、グループに機密ラベルを付けて保存すると、選択したプライバシー設定が適用された機密ラベルのプライバシー設定によって上書きされます。
>
> 以前のバージョンの Outlook クライアントを新しいバージョンにアップグレードすることをお勧めします。

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>シナリオ 2: テナントで従来の AAD[分類](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)が既に使用されている

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>ケース A: テナントはドキュメントおよび電子メールの機密ラベルを使用していません

1. [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)では、既存の従来の Azure AD ラベルと同じ名前の機密ラベルを作成することをお勧めします。
2. このような機密ラベルを名前マッピングを使用して既存の Microsoft 365 グループおよび SharePoint サイトに適用するには、PowerShell コマンドレットを使用します。
3. 管理者は、従来の Azure AD ラベルを削除することを選択できます。
    - 互換性のあるワークロードでは、これらの機密ラベルおよびグループによって作成されたものが表示されます。
    - 非互換のワークロードはグループを作成するときには動作しますが、機密ラベルが添付されていません。
4. 管理者は、PowerShell コマンドレットを実行して、ラベルなしでこれらのグループに機密ラベルを適用できます。
    - 別の方法として、管理者は従来の Azure AD ラベルを保持することもできます。
        - 互換性のあるワークロードでは、これらの機密ラベルが表示され、グループによって作成されます。 互換性のあるワークロードは、機密ラベルをサポートするサービスです。
        - 互換性のないワークロードは、グループを作成するとき、および従来の Azure AD ラベルを表示するときに機能します。 これらの従来の Azure AD ラベルは、互換性のないワークロードを使用して作成されたこれらのグループに接続されます。
5. 管理者は、PowerShell コマンドレットを実行して、従来の Azure AD ラベルでこれらのグループに機密ラベルを適用することを強くお勧めします。

表 2.  互換性があり、互換性のないワークロードの動作–グループを作成、編集、または削除する

|ワークロード|グループウィンドウでユーザーに表示されるラベルの一覧|新しいグループを作成する |グループの編集 |Delete group |
|:-------|:-------|:--------|:--------|:--------|   
|動作   |機密ラベル |動作に変更はありません。 |動作に変更はありません。 |動作に変更はありません。 |
|互換性のない |以前の従来の AAD ラベル。 |ユーザーは、従来の Azure AD ラベルが選択されたグループを作成できます。 <br><br>注: 管理者はコマンドレットを実行して、バックグラウンドで機密ラベルを適用できます。 |**ケース 1**: 以前に選択した機密ラベルがありません。 ユーザーはグループを編集できます。<br><br> **ケース 2**: 以前に選択された、従来の AAD ラベル。 ユーザーはグループを編集できます。<br><br> **ケース 3**: 以前にコマンドレットを使用してバックグラウンドで適用した機密ラベル。 ユーザーがグループを編集できるようにする必要があります。1つのケースを除き、ユーザーはラベルに関してプライバシー設定の無効な組み合わせを選択します。 |ユーザーはグループを削除できます。 |

> [!NOTE]
> Outlook デスクトップクライアント (Win 32) の場合、管理者がテナントで機密ラベルを有効にし、ユーザーが以前のバージョンの Outlook デスクトップクライアント (Win 32) を使用しています。
>
> - ユーザーには、Outlook デスクトップクライアントの古いバージョンに機密ラベルが表示されます。
> - ただし、ユーザーがグループを編集して、グループに機密ラベルを付けて保存すると、選択したプライバシー設定が適用された機密ラベルのプライバシー設定によって上書きされます。
>
> 以前のバージョンの Outlook クライアントを新しいバージョンにアップグレードすることをお勧めします。

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>ケース B: ドキュメントと電子メールに使用されるテナントの機密ラベル

1. 管理者がテナントで機密ラベル機能を有効にしたときに、テナントフラグ ' EnableMIPLabels ' を true に設定すると、[グループ/サイト/チームの作成および編集] ダイアログボックスの [ドキュメントと電子メールの秘密度] ラベルが表示されるようになります。
2. 管理者は、同じドキュメントとメールの機密ラベルを使用して、関連するグループ設定を指定することによって、グループ/サイト/チームに対してプライバシーおよび外部ユーザーアクセスを強制することができます。
    1. [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で、[**サイトとグループ**] タブを選択します。
    2. ドキュメントまたはメールの秘密度ラベルを編集します。

## <a name="sample-script"></a>サンプル スクリプト

従来の AAD ラベルを持つグループを機密ラベルに移行するサンプルスクリプトについては、「 [従来の AZURE AD グループの分類](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)」を参照してください。

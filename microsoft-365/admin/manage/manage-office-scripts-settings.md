---
title: Office スクリプトの設定を管理する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: 組織内のユーザーのスクリプトOffice設定を管理する方法について学習します。
ms.openlocfilehash: 103c8a6ce2e71cf5cb3660d4ed8b3aadbd249ff3b37b76ef5243c6132b8cfe54
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53825057"
---
# <a name="manage-office-scripts-settings"></a>Office スクリプトの設定を管理する

[Officeスクリプトを使用](/office/dev/scripts)すると、ユーザーはスクリプトを記録、編集、実行することでタスクを自動化Excel on the web。 Officeスクリプトは、Power Automateと機能し、ユーザーはオンライン (Business) コネクタを使用してブックExcelスクリプトを実行します。 Microsoft 365管理者は、Officeスクリプトの設定を管理Microsoft 365 管理センター。

## <a name="before-you-begin"></a>はじめに

- スクリプト設定Office管理するには、グローバル管理者である必要があります。詳細については、「管理者ロール[について」を参照してください](../add-users/about-admin-roles.md)。

- 組織内のユーザーが、Microsoft 365 または Office 365 の商用プランまたは EDU プランに対して有効なライセンスを持ち、Office デスクトップ アプリ (以下のいずれかのプランなど) にアクセスできます。

- Microsoft 365 Business Standard
- Microsoft 365 Apps for business
- Microsoft 365 Apps for enterprise
- Office 365 E3
- Office 365 E5
- Office 365 A3
- Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>スクリプトの可用性Officeスクリプトの共有を管理する

1. [組織のMicrosoft 365 管理センター] タブの [組織 \> **設定] タブ** \> **[に移動](https://go.microsoft.com/fwlink/p/?linkid=2053743)** します。

2. [スクリプト **Office選択します**。

3. Office既定ではスクリプトが有効になっているので、組織のすべてのユーザーが機能にアクセスして使用し、スクリプトを共有できます。 組織のスクリプトOfficeをオフにする場合は、[ユーザーが組織のタスクを自動化 **Excel on the webオフにします**。

4. 以前に組織の Office スクリプトをオフにし、そのスクリプトを有効に戻す場合は **、[Excel on the web** でユーザーがタスクを自動化する] を選択し、この機能にアクセスして使用できるユーザーを指定します。

    - 組織内のすべてのユーザーがスクリプトにアクセスして使用Officeするには、[すべてのユーザー] **(既定**) を選択のままにします。

    - 特定のグループのメンバーだけが Office スクリプトにアクセスして使用するには、[特定のグループ] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。 許可リストに追加できるグループは 1 つのみであり、次のいずれかの種類である必要があります。
        - Microsoft 365 グループ
        - 配布グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ

        さまざまな種類のグループの詳細については、「グループの比較」 [を参照してください](../create-groups/compare-groups.md)。

5. Office スクリプトへのアクセス権を持つユーザーが組織内の他のユーザーとスクリプトを共有するには **、[Office スクリプト** にアクセスできるユーザーが組織内の他のユーザーとスクリプトを共有する] を選択します。 組織外でのスクリプトの共有は許可されません。

    > [!NOTE]
    > 後で組織のスクリプト共有をオフにした場合でも、ユーザーは以前に共有したスクリプトを実行できます。

6. スクリプトでスクリプトを共有できるユーザー Officeを指定します。

    - スクリプトへのアクセス権を持つすべてのOfficeスクリプトを共有するには、[すべての **ユーザー]** (既定) を選択のままにします。

    - Office スクリプトへのアクセス権を持つ特定のグループのメンバーだけがスクリプトを共有するには、[特定のグループ] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。 許可リストに追加できるグループは 1 つのみであり、次のいずれかの種類である必要があります。
        - Microsoft 365 グループ
        - 配布グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ

        さまざまな種類のグループの詳細については、「グループの比較」 [を参照してください](../create-groups/compare-groups.md)。

7. ユーザーが Power Automate フロー内で Office スクリプトを実行するには、[Office スクリプトへのアクセス権を持つユーザーにスクリプトを実行 **Power Automate。** これにより、ユーザーは[オンライン] ([ビジネス) コネクタExcel実行](/connectors/excelonlinebusiness)スクリプト オプションを使用してフロー ステップ **を追加** できます。

    - スクリプトにアクセスできるすべてのユーザー Officeフローでスクリプトを使用するには、[すべての **ユーザー]** (既定) を選択したままにしてください。

    - Office スクリプトにアクセスできる特定のグループのメンバーだけがフローでスクリプトを使用するには、[特定のグループ]を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。 許可リストに追加できるグループは 1 つのみであり、次のいずれかの種類である必要があります。
        - Microsoft 365 グループ
        - 配布グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ

        さまざまな種類のグループの詳細については、「グループの比較」 [を参照してください](../create-groups/compare-groups.md)。

    - スクリプトを使用してスクリプトを使用Office詳細Power Automate、「スクリプトを使用してスクリプトOffice[実行する」を参照Power Automate。](/office/dev/scripts/develop/power-automate-integration)

8. **[保存]** を選択します。

    Office スクリプトの設定の変更が有効になるまで、最大で 48 時間かかる場合があります。

## <a name="next-steps"></a>次の手順

Office スクリプトは Power Automate で動作しますので、ユーザーが Office スクリプトを使用している間に組織のデータが保護されたままになるために、既存のデータ損失防止 (DLP) ポリシーを確認することをお勧めします。 詳細については、「[データ損失防止 (DLP) ポリシー](/power-automate/prevent-data-loss)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[Officeスクリプトの技術ドキュメント](/office/dev/scripts/)(リンク ページ)\
[[スクリプトOfficeの概要 (](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a)記事Excel)\
[Web OfficeスクリプトExcel共有](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b)する (記事)\
[スクリプトを記録、編集、およびOfficeする (Excel on the web)](/office/dev/scripts/tutorials/excel-tutorial)

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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid: MET150
description: 組織内のユーザーのOffice スクリプト設定を管理する方法について説明します。
ms.openlocfilehash: fdc9c947ee7f12e284fd215f05f8b5c3dcb127eb
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64941151"
---
# <a name="manage-office-scripts-settings"></a>Office スクリプトの設定を管理する

[Office スクリプト](/office/dev/scripts)を使用すると、ユーザーはExcel on the webでスクリプトを記録、編集、実行してタスクを自動化できます。 Office スクリプトはPower Automateで動作し、ユーザーはExcel Online (Business) コネクタを使用してブックでスクリプトを実行します。 Microsoft 365管理者は、Microsoft 365 管理センターからOfficeスクリプト設定を管理できます。

## <a name="before-you-begin"></a>はじめに

- Office スクリプト設定を管理するには、グローバル管理者である必要があります。詳細については、「[管理者ロールについて](../add-users/about-admin-roles.md)」を参照してください。

- 組織内のユーザーが、次のいずれかのプランなど、Office デスクトップ アプリへのアクセスを含むMicrosoft 365またはOffice 365商用または EDU プランの有効なライセンスを持っていることを確認します。

- Microsoft 365 Business Standard
- Microsoft 365 Apps for business
- Microsoft 365 Apps for enterprise
- Office 365 E3
- Office 365 E5
- Office 365 A3
- Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Office スクリプトの可用性とスクリプトの共有を管理する

1. Microsoft 365 管理センターで、[**設定** \> **組織設定** \> **[サービス](https://go.microsoft.com/fwlink/p/?linkid=2053743)**] タブに移動します。

2. **[Office スクリプト] を選択します**。

3. Office スクリプトは既定で有効になっており、組織内のすべてのユーザーが機能にアクセスして使用し、スクリプトを共有できます。 組織のスクリプトOfficeオフにするには、[**ユーザーがExcel on the webでタスクを自動化できるようにする**] チェック ボックスをオフにします。

4. 以前に組織のスクリプトOfficeオフにし、再度有効にする場合は、[**ユーザーがExcel on the webでタスクを自動化できるようにする**] を選択し、この機能にアクセスして使用できるユーザーを指定します。

    - 組織内のすべてのユーザーが Office スクリプトにアクセスして使用できるようにするには、**すべてのユーザー** (既定値) を選択したままにします。

    - 特定のグループのメンバーのみが Office スクリプトにアクセスして使用できるようにするには、[**特定のグループ**] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。 許可リストに追加できるグループは 1 つだけです。次のいずれかの種類である必要があります。
        - Microsoft 365 グループ
        - 配布グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ

        さまざまな種類のグループの詳細については、「グループの [比較](../create-groups/compare-groups.md)」を参照してください。

5. Office スクリプトへのアクセス権を持つユーザーが組織内の他のユーザーとスクリプトを共有 **できるようにするには、[Office スクリプトにアクセスできるユーザーが組織内の他のユーザーとスクリプトを共有できるようにする**] を選択します。 組織外でのスクリプトの共有は許可されません。

    > [!NOTE]
    > 後で組織のスクリプト共有を無効にした場合でも、ユーザーは以前に共有されたスクリプトを実行できます。

6. Office スクリプトにアクセスできるユーザーがスクリプトを共有できるかどうかを指定します。

    - Office スクリプトへのアクセス権を持つすべてのユーザーがスクリプトを共有できるようにするには、**すべての** ユーザー (既定値) を選択したままにします。

    - Office スクリプトへのアクセス権を持つ特定のグループのメンバーのみがスクリプトを共有できるようにするには、[**特定のグループ**] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。 許可リストに追加できるグループは 1 つだけです。次のいずれかの種類である必要があります。
        - Microsoft 365 グループ
        - 配布グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ

        さまざまな種類のグループの詳細については、「グループの [比較](../create-groups/compare-groups.md)」を参照してください。

7. ユーザーがPower Automate フロー内でOfficeスクリプトを実行 **できるようにするには、[Office スクリプトにアクセスできるユーザーがPower Automateでスクリプトを実行できるようにする**] を選択します。 これにより、ユーザーは [Excel Online (Business) コネクタの](/connectors/excelonlinebusiness)**実行スクリプト** オプションを使用してフローステップを追加できます。

    - Office スクリプトへのアクセス権を持つすべてのユーザーがフローでスクリプトを使用できるようにするには、**すべてのユーザー** (既定値) を選択したままにします。

    - Office スクリプトへのアクセス権を持つ特定のグループのメンバーのみがフローでスクリプトを使用できるようにするには、[**特定のグループ**] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。 許可リストに追加できるグループは 1 つだけです。次のいずれかの種類である必要があります。
        - Microsoft 365 グループ
        - 配布グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ

        さまざまな種類のグループの詳細については、「グループの [比較](../create-groups/compare-groups.md)」を参照してください。

    - Power Automateで Office スクリプトを使用する方法の詳細については、「[Power Automateを使用したOffice スクリプトの実行](/office/dev/scripts/develop/power-automate-integration)」を参照してください。

8. **[保存]** を選択します。

    Office スクリプトの設定の変更が有効になるまで、最大で 48 時間かかる場合があります。

## <a name="next-steps"></a>次の手順

Office スクリプトはPower Automateと連携するため、既存の Microsoft Purview データ損失防止 (DLP) ポリシーを確認して、ユーザーが Office スクリプトを使用している間、組織のデータが保護されたままであることを確認することをお勧めします。 詳細については、「[データ損失防止 (DLP) ポリシー](/power-automate/prevent-data-loss)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[Office スクリプトの技術ドキュメント](/office/dev/scripts/) (リンク ページ)\
[ExcelのOfficeスクリプトの概要](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (記事)\
[Web のExcelでOfficeスクリプトを共有する](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (記事)\
[Excel on the webでOfficeスクリプトを記録、編集、作成する](/office/dev/scripts/tutorials/excel-tutorial) (記事)

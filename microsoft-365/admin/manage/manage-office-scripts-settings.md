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
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 組織内のユーザーのOfficeスクリプト設定を管理する方法について説明します。
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572311"
---
# <a name="manage-office-scripts-settings"></a>Office スクリプトの設定を管理する

[Officeスクリプト](/office/dev/scripts)を使用すると、ユーザーは Web 上のExcelでスクリプトを記録、編集、実行することでタスクを自動化できます。 OfficeスクリプトはPower Automateと連携し、ユーザーはオンライン (ビジネス) コネクタを使用してワークブックでスクリプトを実行Excel。 Microsoft 365管理者は、Microsoft 365管理センターからOfficeスクリプト設定を管理できます。

## <a name="before-you-begin"></a>始める前に

- Officeスクリプト設定を管理するには、グローバル管理者である必要があります。詳細については、「[管理者ロールについて](../add-users/about-admin-roles.md)」を参照してください。

- 組織内のユーザーが、次のいずれかのプランなど、Office デスクトップ アプリへのアクセスを含む、Microsoft 365またはOffice 365の商用または EDU プランの有効なライセンスを持っていることを確認します。

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps for business
    - Microsoft 365 Apps for enterprise
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Officeスクリプトの可用性とスクリプトの共有を管理する

1. Microsoft 365管理センターで、[組織設定のサービス **] タブ設定** \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a>します。

2. [**スクリプトOffice] を** 選択します。

3. Officeスクリプトは既定で有効になっており、組織内の全員が機能にアクセスして使用したり、スクリプトを共有したりできます。 組織のOfficeスクリプトをオフにするには、[**ユーザーがExcel on the webでタスクを自動化できるようにする**] チェック ボックスをオフにします。

4. 以前に組織のスクリプトOfficeをオフにして、それをオンに戻す場合は、[**ユーザーがExcel on the webでタスクを自動化できるようにする**] をオンにし、その機能にアクセスして使用できるユーザーを指定します。

    - 組織内のすべてのユーザーが Officeスクリプトにアクセスして使用できるようにするには、[**すべてのユーザー** ](既定値)を選択したままにします。

    - 特定のグループのメンバーのみがOfficeスクリプトにアクセスして使用できるようにするには、[特定の **グループ**] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。 許可一覧に追加できるグループは 1 つだけで、次のいずれかの種類である必要があります。
        - Microsoft 365グループ
        - 配送グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ
    
        さまざまな種類のグループの詳細については、「グループの [比較](../create-groups/compare-groups.md)」を参照してください。

5. Office スクリプトへのアクセス権を持つユーザーが組織内の他のユーザーとスクリプトを共有できるようにするには **、[Office スクリプトへのアクセス権を持つユーザーが組織内の他のユーザーとスクリプトを共有できるようにする**] チェック ボックスをオンにします。 組織外でのスクリプトの共有は許可されていません。
 
    > [!NOTE]
    > 後で組織のスクリプト共有を無効にしても、ユーザーは以前に共有されたスクリプトを実行できます。
 
6. スクリプトを共有できるOfficeスクリプトにアクセスできるユーザーを指定します。
    
    - Officeスクリプトへのアクセス権を持つすべてのユーザーがスクリプトを共有できるようにするには、[**すべてのユーザー** ](デフォルト)を選択したままにします。

    - Officeスクリプトへのアクセス権を持つ特定のグループのメンバーのみがスクリプトを共有できるようにするには、[**特定のグループ**] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。 許可一覧に追加できるグループは 1 つだけで、次のいずれかの種類である必要があります。
        - Microsoft 365グループ
        - 配送グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ
    
        さまざまな種類のグループの詳細については、「グループの [比較](../create-groups/compare-groups.md)」を参照してください。

7. ユーザーがPower Automateフロー内でOfficeスクリプトを実行できるようにするには **、[OfficeスクリプトにアクセスできるユーザーがPower Automateでスクリプトを実行できるようにする**] を選択します。 これにより、ユーザーは [、オンライン (ビジネス) コネクタ](/connectors/excelonlinebusiness)の **スクリプトの実行** オプションExcelを使用してフロー ステップを追加できます。

    - Officeスクリプトへのアクセス権を持つすべてのユーザーがフローでスクリプトを使用できるようにするには **、Everyone** (デフォルト) を選択したままにします。

    - Officeスクリプトへのアクセス権を持つ特定のグループのメンバーのみがフローでスクリプトを使用できるようにするには、[**特定のグループ**] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。 許可一覧に追加できるグループは 1 つだけで、次のいずれかの種類である必要があります。
        - Microsoft 365グループ
        - 配送グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ

        さまざまな種類のグループの詳細については、「グループの [比較](../create-groups/compare-groups.md)」を参照してください。

    - Power AutomateでOfficeスクリプトを使用する方法の詳細については[、「Power AutomateでOfficeスクリプトを実行](/office/dev/scripts/develop/power-automate-integration)する」を参照してください。

8. **[保存]** を選択します。

    Officeスクリプトの設定の変更が有効になるためには、最大 48 時間かかることがあります。

## <a name="next-steps"></a>次の手順

OfficeスクリプトはPower Automateと連携するため、既存のデータ損失防止 (DLP) ポリシーを確認して、ユーザーがOffice スクリプトを使用している間も組織のデータが保護されたままであることを確認することをお勧めします。 詳細については、「 [データ損失防止 (DLP) ポリシー](/power-automate/prevent-data-loss)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[Office スクリプトのテクニカル ドキュメント](/office/dev/scripts/)(リンク ページ)\
[ExcelのOfficeスクリプトの概要](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a)(記事)\
[Web 用ExcelでOfficeスクリプトを共有](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b)する (記事)\
[Excel on the webでOfficeスクリプトを記録、編集、作成](/office/dev/scripts/tutorials/excel-tutorial)する (記事)

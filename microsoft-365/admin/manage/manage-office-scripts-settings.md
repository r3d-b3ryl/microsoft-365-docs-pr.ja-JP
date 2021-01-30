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
description: 組織内のユーザーの Office設定を管理する方法について学習します。
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058425"
---
# <a name="manage-office-scripts-settings"></a>Office スクリプトの設定を管理する

Officeスクリプトを使用すると、Excel on the web でスクリプトを記録、編集、および実行することにより、タスクを自動化できます。 Officeスクリプトは Power Automate で動作し、ユーザーは Excel Online (Business) コネクタを使用してブック上でスクリプトを実行します。 Microsoft 365 管理者は、Microsoft 365 Officeスクリプトの設定を管理できます。

## <a name="before-you-begin"></a>はじめに

- スクリプトのOffice管理するには、グローバル管理者である必要があります。詳細については、「管理者ロール [について」を参照してください](../add-users/about-admin-roles.md)。

- 組織内のユーザーが、次のいずれかのプランなど、Office デスクトップ アプリへのアクセスを含む Microsoft 365 または Office 365 の商用または EDU プランの有効なライセンスを持っている必要があります。

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps for business
    - Microsoft 365 Apps for enterprise
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>スクリプトとスクリプトOfficeの可用性を管理する

1. Microsoft 365 管理センターで **、[Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services]</a> タブに移動します。

2. [スクリプト **Office選択します**。

3. Officeスクリプトは既定でオンにされ、組織内のすべてのユーザーが機能にアクセスして使用し、スクリプトを共有できます。 組織のスクリプトOfficeオフにする場合は、[ユーザーが Excel **on the web** でタスクを自動化する] チェック ボックスをオフにします。

4. 以前に組織の Office スクリプトをオフにし、再び有効にする場合は、[ユーザーが **Excel on the web** でタスクを自動化する] を選択し、この機能にアクセスして使用できるユーザーを指定します。

    - 組織内のすべてのユーザーがスクリプトにアクセスして使用Officeするには、[すべての **ユーザー]** (既定) を選択したままにします。

    - 特定のグループのメンバーにのみ Office Scripts へのアクセスと使用を許可するには、[特定のグループ] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。 許可リストに追加できるグループは 1 つだけで、次のいずれかの種類である必要があります。
        - Microsoft 365 グループ
        - 配布グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ
    
        さまざまな種類のグループの詳細については、「グループの比較」を [参照してください](../create-groups/compare-groups.md)。

5. Office スクリプトにアクセスできるユーザーが組織内の他のユーザーとスクリプトを共有するには **、[Office スクリプト** にアクセスできるユーザーが組織内の他のユーザーとスクリプトを共有する] を選択します。 組織外でのスクリプトの共有は許可されません。
 
    > [!NOTE]
    > 後で組織のスクリプト共有をオフにした場合でも、ユーザーは以前に共有したスクリプトを実行できます。
 
6. スクリプトにアクセスできるユーザーを指定Officeスクリプトを共有できます。
    
    - スクリプトへのアクセス権を持Officeスクリプトを共有するには、[すべての **ユーザー]** (既定) を選択したままにしてください。

    - Office Scripts にアクセスできる特定のグループのメンバーだけがスクリプトを共有するには、[特定のグループ]を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。 許可リストに追加できるグループは 1 つだけで、次のいずれかの種類である必要があります。
        - Microsoft 365 グループ
        - 配布グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ
    
        さまざまな種類のグループの詳細については、「グループの比較」を [参照してください](../create-groups/compare-groups.md)。

7. ユーザーが Power Automate フロー内で Office スクリプトを実行するには **、[Office スクリプト** にアクセスできるユーザーが Power Automate でスクリプトを実行する] を選択します。 これにより、ユーザーは Excel Online [(Business) Connector](/connectors/excelonlinebusiness)の実行スクリプト オプションを使用してフロー **ステップを追加** できます。

    - すべてのユーザーが Office スクリプトをフローで使用するには、[すべての **ユーザー]** (既定) を選択したままにしてください。

    - Office スクリプトにアクセスできる特定のグループのメンバーだけがフロー内でスクリプトを使用するには、[特定のグループ]を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。 許可リストに追加できるグループは 1 つだけで、次のいずれかの種類である必要があります。
        - Microsoft 365 グループ
        - 配布グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ

        さまざまな種類のグループの詳細については、「グループの比較」を [参照してください](../create-groups/compare-groups.md)。

    - データ損失防止ポリシーへの影響を含め、Power Automate で Office スクリプトを使用する方法の詳細については [、「Power Automate](/office/dev/scripts/develop/power-automate-integration)を使用して Office スクリプトを実行する」を参照してください。

8. [**保存**] を選択します。

    スクリプト設定の変更が有効Office、最大 48 時間かかる場合があります。

## <a name="next-steps"></a>次の手順

Office スクリプトは Power Automate と組み合わせるために、既存のデータ損失防止 (DLP) ポリシーを確認して、ユーザーが Office スクリプトを使用している間も組織のデータが保護されたままにすることをお勧めします。 詳細については、「データ損失 [防止 (DLP) ポリシー」を参照してください](/power-automate/prevent-data-loss)。

## <a name="related-content"></a>関連コンテンツ

[Office スクリプトの技術ドキュメント](/office/dev/scripts/) (リンク ページ)\
[Excel Office スクリプトの概要](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (記事)\
[Excel Officeスクリプトを共有する](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (記事)\
[Excel on the web でスクリプトをOffice、編集、および作成する](/office/dev/scripts/tutorials/excel-tutorial) (記事)

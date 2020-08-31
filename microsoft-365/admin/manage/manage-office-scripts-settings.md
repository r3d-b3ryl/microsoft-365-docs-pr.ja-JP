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
description: 組織内のユーザーの Office スクリプト設定を管理する方法について説明します。
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300837"
---
# <a name="manage-office-scripts-settings"></a>Office スクリプトの設定を管理する

Office スクリプトを使用すると、ユーザーは web 上の Excel でスクリプトを記録、編集、および実行することによってタスクを自動化できます。 Office スクリプトは電源自動化と共に動作し、ユーザーは Excel Online (Business) コネクタを使用してブックのスクリプトを実行します。 Microsoft 365 管理者は、Microsoft 365 管理センターから Office スクリプトの設定を管理できます。

## <a name="before-you-begin"></a>はじめに

- Office スクリプトの設定を管理するには、グローバル管理者である必要があります。詳細については、「 [管理者の役割につい](../add-users/about-admin-roles.md)て」を参照してください。

- 組織内のユーザーが、次のプランのいずれかのような Office デスクトップアプリへのアクセスを含む、Microsoft 365 または Office 365 コマーシャルまたは EDU プランの有効なライセンスを所有していることを確認します。

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps for business
    - Microsoft 365 Apps for enterprise
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Office スクリプトの可用性およびスクリプトの共有を管理する

1. Microsoft 365 管理センターで、[設定] [ **Settings** \> **組織設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">サービス</a>] タブに移動します。

2. [ **Office スクリプト**] を選択します。

3. Office スクリプトは既定で有効になっており、組織内のすべてのユーザーが機能にアクセスして使用し、スクリプトを共有できます。 組織の Office スクリプトを無効にするには、[ **ユーザーが web 上の Excel でタスクを自動化できる** ようにする] チェックボックスをオフにします。

4. 以前に組織の Office スクリプトをオフにしていて、再度有効にする場合は、[ **ユーザーに web 上の Excel でのタスクの自動化を許可**する] を選択し、機能にアクセスして使用できるユーザーを指定します。

    - 組織内のすべてのユーザーが Office スクリプトにアクセスして使用できるようにするには、 **[すべてのユーザー] (既定** 値) を選択したままにします。 

    - 特定のグループのメンバーのみが Office スクリプトにアクセスして使用できるようにするには、[ **特定のグループ**] を選択し、グループの名前または電子メールエイリアスを入力して許可リストに追加します。 許可リストには、グループを1つだけ追加できます。また、次のいずれかの種類である必要があります。
        - Microsoft 365 グループ
        - 配布グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ
    
        さまざまな種類のグループの詳細については、「 [グループを比較](../create-groups/compare-groups.md)する」を参照してください。

5. Office スクリプトへのアクセス権を持つユーザーが組織内の他のユーザーとスクリプトを共有できるようにするには、[ **Office スクリプトへのアクセス権を持つユーザーが組織内の他のユーザーとスクリプトを共有**できるようにする] を選択します。 組織外のスクリプトの共有は許可されていません。
 
    > [!NOTE]
    > 後で組織のスクリプト共有を無効にした場合でも、ユーザーは以前に共有されたスクリプトを実行できます。
 
6. Office スクリプトにアクセスできるユーザーを指定して、スクリプトを共有できます。
    
    - Office スクリプトへのアクセス権を持つすべてのユーザーがスクリプトを共有できるようにするには、 **[すべてのユーザー (既定** )] を選択したままにします。

    - Office スクリプトへのアクセス権を持つ特定のグループのメンバーのみがスクリプトを共有できるようにするには、[ **特定のグループ**] を選択し、グループの名前または電子メールエイリアスを入力して許可リストに追加します。 許可リストには、グループを1つだけ追加できます。また、次のいずれかの種類である必要があります。
        - Microsoft 365 グループ
        - 配布グループ
        - セキュリティ グループ
        - メールが有効なセキュリティ グループ
    
        さまざまな種類のグループの詳細については、「 [グループを比較](../create-groups/compare-groups.md)する」を参照してください。

7. **[保存]** を選択します。

    Office スクリプト設定の変更が有効になるまで、最大48時間かかる場合があります。

## <a name="next-steps"></a>次の手順

Office スクリプトはパワー自動処理に対応しているため、既存のデータ損失防止 (DLP) ポリシーを確認して、ユーザーが Office スクリプトを使用している間も、組織のデータが保護されたままになるようにすることをお勧めします。 詳細については、「 [データ損失防止 (DLP) ポリシー](/power-automate/prevent-data-loss)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[Office スクリプトの技術ドキュメント](/office/dev/scripts/) (リンクページ) \
[Excel での Office スクリプトの概要](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (記事) \
[Web 用の Excel で Office スクリプトを共有](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) する (記事) \
[Excel on the web で Office スクリプトを記録、編集、および作成する](/office/dev/scripts/tutorials/excel-tutorial) (記事)
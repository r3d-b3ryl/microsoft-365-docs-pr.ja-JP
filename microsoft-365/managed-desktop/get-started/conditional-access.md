---
title: 登録後に設定を調整する
description: 特定の Microsoft アカウントを除外する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e78f0123c909c90ff90be913e8775cc1e5b30313
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777101"
---
# <a name="adjust-settings-after-enrollment"></a>登録後に設定を調整する

Microsoft マネージド デスクトップへの登録が完了したら、この記事で指定されている Microsoft Intune と Azure Active Directory (Azure AD) の設定を調整して、セキュリティを管理および維持する必要があります。 Microsoft マネージド デスクトップ デバイスとユーザーを含む特定の Azure AD グループを除外するには、次の設定を設定します。 グループを除外する手順については、「条件付きアクセス [: ユーザーとグループ」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)。

> [!NOTE]
> Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーへの登録後に変更を行った場合、Microsoft マネージド デスクトップの正常な動作が停止する可能性があります。 Microsoft マネージド デスクトップの操作に関する問題を回避するには、「準備状況[](../get-ready/readiness-assessment-fix.md)評価ツールで見つかった問題を修正する」で説明されている特定の設定を確認してから、ポリシーを変更してください。


## <a name="microsoft-intune-settings"></a>Microsoft Intune の設定

- Autopilot 展開プロファイル: 会社の管理者によって作成された Autopilot プロファイルの場合は **、Modern Workplace Devices -All** Azure AD グループを除外します。 手順については [、「Windows Autopilot を使用して Intune に Windows デバイスを登録する」を参照してください](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。 モダン Workplace **Devices -All** Azure AD グループは、名前に "Modern Workplace" が含む Microsoft マネージド デスクトップによって作成された展開ポリシー **(Modern Workplace Autopilot Profile** など) から除外しなけ。 
- 条件付きアクセス ポリシー: 会社の管理者によって作成された条件付きアクセス ポリシーの場合は、モダン **Workplace Service アカウント** Azure ADします。 手順については、「条件付きアクセス [: ユーザーとグループ」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 モダン Workplace **Devices -All** Azure AD グループは、名前に "Modern Workplace" が含む Microsoft マネージド デスクトップによって作成されたポリシー **(Modern Workplace Secure Workstation** など) から除外してください。
- 多要素認証: 多要素認証を必要とする会社の管理者が作成した条件付きアクセス ポリシーで **、モダン** ワークプレース サービス アカウント Azure ADしてください。 詳細については、「条件付きアクセス ポリシー [と条件付きアクセス](../get-ready/readiness-assessment-fix.md#conditional-access-policies) : すべてのユーザーに MFA を要求する」 [を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。
- セキュリティベースライン: 会社の管理者によって作成されたセキュリティ基本ポリシーの場合は、 **モダン Workplace Devices -All**  Azure AD グループを除外します。 手順については、「セキュリティベースライン [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/security-baselines)。 モダン Workplace **Devices -All** Azure AD グループは、名前に "Modern Workplace" が含む Microsoft マネージド デスクトップによって作成されたポリシー (Modern Workplace Security Baseline など) から除外 **しな** け。
- Windows 10 更新リング: 会社の管理者によって作成された Windows 10 更新リング ポリシーの場合は **、Modern Workplace Devices -All**  Azure AD グループを除外します。 手順については、「Intune での [Windows 10 ソフトウェア更新プログラムの管理」を参照してください](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。 モダン Workplace **Devices -All** Azure AD グループは、名前に "Modern Workplace" が含む Microsoft マネージド デスクトップによって作成されたポリシー (Modern **Workplace Update** ポリシーなど) から除外しなけ。


## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

セルフサービスによるパスワードのリセット: **[選択** した設定] を選択し、[ **モダン Workplace Devices] -[すべての** Azure AD グループ] を選択します。 詳細については、「チュートリアル: Azure Active Directory のセルフサービス によるパスワードのリセットを使用して、ユーザーが自分のアカウントのロックを解除したり、パスワード [をリセットしたりできる」を参照してください](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップの使用を開始する手順

1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)
2. 登録後に設定を調整する (この記事)
3. [ライセンスを割り当てる](assign-licenses.md)
4. [Intune 会社ポータルを展開する](company-portal.md)
5. [Enterprise State Roaming を有効にする](enterprise-state-roaming.md)
6. [デバイスをセットアップする](set-up-devices.md)
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)
8. [アプリを展開する](deploy-apps.md)

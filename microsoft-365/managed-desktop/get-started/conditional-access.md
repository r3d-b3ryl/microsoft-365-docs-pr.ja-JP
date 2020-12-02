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
ms.openlocfilehash: 76a73372cc7517c3241390e58c28b0b02bffd664
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527699"
---
# <a name="adjust-settings-after-enrollment"></a>登録後に設定を調整する

Microsoft マネージドデスクトップでの登録を完了した後、特定の Microsoft Intune および Azure Active Directory (Azure AD) の設定を調整して、セキュリティを管理および管理できるようにする必要があります。 次の設定を設定して、Microsoft Managed Desktop デバイスとユーザーを含む Azure AD グループを除外します。 グループを除外する手順については、「 [条件付きアクセス: ユーザーとグループ](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)」を参照してください。

## <a name="microsoft-intune-settings"></a>Microsoft Intune の設定

- 自動操縦展開プロファイル: **モダン Workplace Devices-すべて**  の Azure AD グループを除外します。 手順については、「 [Windows 自動操縦を使用した Intune での windows デバイスの登録](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)」を参照してください。
- 条件付きアクセスポリシー: **モダン Workplace Service アカウント** の Azure AD グループを除外します。 手順については、「 [条件付きアクセス: ユーザーとグループ](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)」を参照してください。
- 多元的な認証: 多要素認証を必要とする条件付きアクセスポリシーでは、 **モダンワークプレースサービスアカウント** の Azure AD グループを除外してください。 詳細については、「 [条件付きアクセスポリシー](../get-ready/readiness-assessment-fix.md#conditional-access-policies) と [条件付きアクセス: すべてのユーザーに MFA を必須にする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)」を参照してください。
- セキュリティベースライン: **モダン Workplace Devices-すべて**  の Azure AD グループを除外します。 手順については、「 [セキュリティ基準を使用して Intune で Windows 10 デバイスを構成する](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。
- Windows 10 更新リング: **モダン Workplace Devices-すべて**  の Azure AD グループを除外します。 手順については、「 [Intune で Windows 10 ソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する」を参照してください。


## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

セルフサービスによるパスワードのリセット: **選択した** 設定を選択し、[ **モダン Workplace Devices-すべての** Azure AD グループ] を選択します。 詳細については、「 [チュートリアル: ユーザーがアカウントのロックを解除するか、Azure Active Directory のセルフサービスによるパスワードのリセットを使用してパスワードをリセットする](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)」を参照してください。



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップの使用を開始する手順

1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)
2. 登録後に設定を調整する (この記事)
3. [ライセンスを割り当てる](assign-licenses.md)
4. [Intune 会社ポータルを展開する](company-portal.md)
5. [Enterprise State Roaming を有効にする](enterprise-state-roaming.md)
6. [デバイスをセットアップする](set-up-devices.md)
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)
8. [アプリを展開する](deploy-apps.md)

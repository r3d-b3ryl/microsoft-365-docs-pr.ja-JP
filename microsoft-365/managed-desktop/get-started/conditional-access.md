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
ms.openlocfilehash: d7fe410f114d43d4f6c983aaf23d949298635318
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760105"
---
# <a name="adjust-settings-after-enrollment"></a>登録後に設定を調整する

Microsoft マネージド デスクトップへの登録が完了したら、特定の Microsoft Intune と Azure Active Directory (Azure AD) の設定を調整して、セキュリティを管理および維持する必要があります。 Microsoft マネージド デスクトップ デバイスとユーザーを含む Azure ADグループを除外するには、次の設定を設定します。 グループを除外する手順については、「条件付きアクセス [: ユーザーとグループ」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)。

> [!NOTE]
> Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーへの登録後に変更を加えた場合、Microsoft マネージド デスクトップの正常な動作が停止する可能性があります。 Microsoft マネージド デスクトップの操作で問題が発生しないようにするには、「準備状況評価[](../get-ready/readiness-assessment-fix.md)ツールで見つかった問題を修正する」で説明されている特定の設定を確認してから、ポリシーを変更してください。


## <a name="microsoft-intune-settings"></a>Microsoft Intune の設定

- Autopilot 展開プロファイル: **Modern Workplace Devices -All**  Azure AD グループを除外します。 手順については [、「Windows Autopilot を使用して Intune に Windows デバイスを登録する」を参照してください](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。
- 条件付きアクセス ポリシー: **モダン ワーク** プレース サービス アカウント Azure AD除外します。 手順については、「条件付きアクセス [: ユーザーとグループ」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。
- 多要素認証: 多要素認証を必要とする条件付きアクセス ポリシーで、 **モダン Workplace Service アカウント** Azure ADしてください。 詳細については、「条件付きアクセス ポリシー [と条件付きアクセス](../get-ready/readiness-assessment-fix.md#conditional-access-policies) : すべてのユーザーに MFA を要求する」 [を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。
- セキュリティベースライン: **モダン Workplace Devices -All**  Azure ADグループを除外します。 手順については、「セキュリティベースライン [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/security-baselines)。
- Windows 10 更新リング: **Modern Workplace Devices -All**  Azure AD グループを除外します。 手順については、「Intune での [Windows 10 ソフトウェア更新プログラムの管理」を参照してください](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。


## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

セルフサービスによるパスワードのリセット: **[選択** した設定] を選択し、[ **モダン Workplace Devices] -All** Azure ADします。 詳細については、「チュートリアル: Azure Active Directory のセルフサービス によるパスワードのリセットを使用して、ユーザーが自分のアカウントのロックを解除したり、パスワード [をリセットしたりできる」を参照してください](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップの使用を開始する手順

1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)
2. 登録後に設定を調整する (この記事)
3. [ライセンスを割り当てる](assign-licenses.md)
4. [Intune 会社ポータルを展開する](company-portal.md)
5. [Enterprise State Roaming を有効にする](enterprise-state-roaming.md)
6. [デバイスをセットアップする](set-up-devices.md)
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)
8. [アプリを展開する](deploy-apps.md)

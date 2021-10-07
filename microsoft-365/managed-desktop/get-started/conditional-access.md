---
title: 登録後に設定を調整する
description: 特定の Microsoft アカウントを除外する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c46932ea1173e515d0c3b880cb20a80b247ae586
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202693"
---
# <a name="adjust-settings-after-enrollment"></a>登録後に設定を調整する

登録が完了したら、Microsoft マネージド デスクトップ管理設定を調整する必要があります。 必要に応じて確認および調整するには、次の手順を実行します。

1. 次のセクションMicrosoft Intune説明Azure Active Directory設定を確認します。
2. 環境に適用される項目がある場合は、説明した調整を行います。
3. すべての設定が正しいか再確認する場合は、準備状況評価ツールを再実行[](https://aka.ms/mmdart)して、他の設定と競合Microsoft マネージド デスクトップ。

> [!NOTE]
> Microsoft マネージド デスクトップ に影響を与える Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーに登録した後に変更を加えた場合、Microsoft マネージド デスクトップ が正常に動作しなくる可能性があります。 サービスの問題を回避するには、「準備状況評価ツールで見つかった[](../get-ready/readiness-assessment-fix.md)問題を修正する」で説明されている特定の設定を確認してから、そこに表示されているポリシーを変更します。 準備状況評価ツールをいつでも再実行することもできます。


## <a name="microsoft-intune-settings"></a>Microsoft Intune設定

- Autopilot 展開プロファイル: 自動パイロット ポリシーを使用する場合は、各ポリシーを更新して、モダン **Workplace デバイス -All** Azure AD グループを除外します。 それらを更新するには、[割り当て] の[除外されたグループ] セクションで、登録中に作成されたモダン Workplace デバイス **-all** Azure AD グループMicrosoft マネージド デスクトップします。 Microsoft マネージド デスクトップ、Autopilot プロファイルが作成され、名前に "モダン ワークプレース" (モダン ワークプレース **の自動** パイロット プロファイル) が含されます。 独自の Autopilot プロファイルを更新する場合は、Microsoft マネージド デスクトップによって作成されたモダン Workplace **Autopilot プロファイル** からモダン ワークプレース デバイス **-All** Azure AD グループを除外しない必要があります。

- 条件付きアクセス ポリシー: Microsoft マネージド デスクトップ 登録後に Azure AD、Microsoft Intune、または Microsoft Defender for Endpoint に関連する新しい条件付きアクセス ポリシーを作成する場合は、モダン ワークプレース サービス アカウント **Azure** AD グループを除外します。 手順については、「条件付き [アクセス: ユーザーとグループ」を参照してください](/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 Microsoft マネージド デスクトップ、これらのアカウントへのアクセスを制限するための個別の条件付きアクセス ポリシーを維持します。 条件付きアクセス Microsoft マネージド デスクトップ (**モダン ワーク** プレース – セキュア ワークステーション) を確認するには、[エンドポイントセキュリティ] の [Microsoft エンドポイント マネージャー に移動し、[条件付きアクセス]**に移動します**。 名前に "モダン ワークプレース" ADが含Microsoft マネージド デスクトップ条件付きアクセス ポリシーを変更しない。

- 多要素認証: Microsoft マネージド デスクトップ 登録後に Azure AD、Intune、または Microsoft Defender for Endpoint に関連する条件付きアクセス ポリシーで新しい多要素認証要件を作成する場合は、モダン ワークプレース サービス アカウント **Azure** AD グループを除外します。 手順については、「条件付き [アクセス: ユーザーとグループ」を参照してください](/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 Microsoft マネージド デスクトップグループのメンバーへのアクセスを制限するための個別の条件付きアクセス ポリシーを維持します。 条件付きアクセス Microsoft マネージド デスクトップ (モダン ワークプレース **-)** を確認するには、[エンドポイント セキュリティ] の [Microsoft エンドポイント マネージャー に移動し、[条件付き **アクセス**]**に移動します**。 

- Windows 10リング: 作成したWindows 10更新リング ポリシーの場合は、モダン ワークプレース デバイス **-** すべての Azure AD グループを各ポリシーから除外します。 手順については、「更新リングの [作成と割り当て」を参照してください](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings)。 Microsoft マネージド デスクトップでは、いくつかの更新リング ポリシーも作成され、そのすべてが名前に "モダン ワークプレース" が含されます (たとえば、モダン ワークプレース更新ポリシー **[Broad]**、Modern Workplace Update Policy **[Fast]**、Modern Workplace Update Policy **[First]、** およびモダン ワークプレース更新ポリシー **[Test]** など)。 独自のポリシーを更新する場合は、モダン ワークプレース デバイス **-すべての** Azure AD グループを作成したグループからMicrosoft マネージド デスクトップしてください。


## <a name="azure-active-directory-settings"></a>Azure Active Directory設定

セルフサービス パスワードのリセット: すべてのユーザーにセルフサービス パスワードリセットを使用する場合は、割り当てを調整して、サービス アカウントMicrosoft マネージド デスクトップします。 この割り当てを調整するには *、Microsoft マネージド デスクトップ* サービス アカウントを除くすべてのユーザーに対して Azure AD 動的グループを作成し、そのグループを "すべてのユーザー" ではなく割り当てに使用します。

サービス アカウントを見つけて除外するために、次に使用できる動的クエリの例を示します。

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

このクエリでは、テナント ドメイン@TENANTを置き換える必要があります。



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>データの使用を開始するMicrosoft マネージド デスクトップ

1. [管理ポータル](access-admin-portal.md)にアクセスします。
1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)。
1. 登録後に設定を調整します (この記事)。
1. [Intune ポータル サイト](company-portal.md)を展開して割り当てます。
1. [ライセンスを割り当てる](assign-licenses.md)。
1. [アプリを展開する](deploy-apps.md)。
1. [デバイスをセットアップする](set-up-devices.md)。
1. [Autopilot と登録ステータス ページの初回実行時エクスペリエンス](esp-first-run.md)のセットアップ。
1. [ユーザー サポート機能を有効にする](enable-support.md)。
1. [ユーザーがデバイスを使えるようにする](get-started-devices.md)。
1. [アプリ制御の使用を開始する](get-started-app-control.md)。
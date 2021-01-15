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
ms.openlocfilehash: ca919798480698f92bba094c3755b3eccce30888
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867972"
---
# <a name="adjust-settings-after-enrollment"></a>登録後に設定を調整する

Microsoft マネージド デスクトップへの登録が完了したら、一部の管理設定の調整が必要になる場合があります。 必要に応じて確認および調整するには、次の手順を実行します。

1. 次のセクションで説明する Microsoft Intune と Azure Active Directory の設定を確認します。
2. 環境に適用される項目がある場合は、説明されている調整を行います。
3. すべての設定が正しいか再確認する場合は、準備状況評価ツールを再実行[](https://aka.ms/mmdart)して、Microsoft マネージド デスクトップと競合しないか確認できます。

> [!NOTE]
> 数か月後に運用が続く場合、Microsoft マネージド デスクトップに影響を与える Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーの登録後に変更を加えた場合、Microsoft マネージド デスクトップの正常な動作が停止する可能性があります。 サービスの問題を回避するには、「準備状況評価ツールで見つかった[](../get-ready/readiness-assessment-fix.md)問題を修正する」で説明されている特定の設定を確認してから、そこにリストされているポリシーを変更してください。 準備状況評価ツールは、いつでも再実行できます。


## <a name="microsoft-intune-settings"></a>Microsoft Intune の設定

- Autopilot 展開プロファイル: Autopilot ポリシーを使用する場合は、各ポリシーを更新して、 **モダン Workplace Devices -All** Azure AD グループを除外します。 それらを更新するには、[割り当て] の[除外するグループ] セクションで、Microsoft マネージド デスクトップの登録時に作成されたモダン **Workplace Devices -All** Azure AD グループを選択します。 Microsoft マネージド デスクトップでは、Autopilot プロファイルも作成されます。このプロファイルには、名前に "Modern Workplace" **(Modern Workplace Autopilot Profile) が含されます**。 独自の Autopilot プロファイルを更新する場合は、Microsoftマネージド デスクトップによって作成された Modern **Workplace Autopilot プロファイル** から Modern Workplace **Devices -All** Azure AD グループを除外しなことを確認します。

- 条件付きアクセス ポリシー: Microsoft マネージド デスクトップの登録後に Azure AD、Microsoft Intune、またはエンドポイント用 Microsoft Defender に関連する新しい条件付きアクセス ポリシーを作成する場合は、モダン Workplace **Service アカウント** Azure AD グループを除外します。 手順については、「条件付きアクセス [: ユーザーとグループ」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 Microsoft マネージド デスクトップでは、これらのアカウントへのアクセスを制限するための個別の条件付きアクセス ポリシーを維持しています。 Microsoft マネージド デスクトップの条件付きアクセス ポリシー **(Modern Workplace – Secure Workstation)** を確認するには、Microsoft Endpoint Manager に移動し、Endpoint Security の **条件付きアクセス** に **移動します**。 名前に "モダン ワークプレース" が含AD Microsoft マネージド デスクトップによって作成された条件付きアクセス ポリシーを使用して Azure アプリを変更し、変更を行う必要があります。

- 多要素認証: Microsoft マネージド デスクトップの登録後に Azure AD、Intune、または Microsoft Defender for Endpoint に関連する条件付きアクセス ポリシーで新しい多要素認証要件を作成する場合は、Azure AD のモダン ワークプレース サービス アカウント グループを除外します。 手順については、「条件付きアクセス [: ユーザーとグループ」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 Microsoft マネージド デスクトップでは、このグループのメンバーへのアクセスを制限するための個別の条件付きアクセス ポリシーを維持しています。 Microsoft マネージド デスクトップの条件付きアクセス ポリシー (**モダン ワーク** プレース - ) を確認するには、Microsoft Endpoint Manager に移動し、Endpoint Security の **条件付きアクセス** に **移動します**。 

- Windows 10 更新リング: 作成した Windows 10 更新リング ポリシーの場合は、各ポリシーから **Modern Workplace Devices -All** Azure AD グループを除外します。 手順については、「更新リングを [作成して割り当てる」を参照してください](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings)。 Microsoft マネージド デスクトップでは、更新リング ポリシーもいくつか作成され、そのすべてには名前に "Modern Workplace" があります (たとえば **、Modern Workplace Update Policy [Broad]、Modern** **Workplace Update Policy [Fast]、Modern** **Workplace Update Policy [First]、** および **Modern Workplace Update Policy [Test]** など)。 独自のポリシーを更新する場合は、Microsoft マネージドデスクトップが作成したグループからモダン **Workplace Devices -All** Azure AD グループを除外しなことを確認してください。


## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

セルフサービスによるパスワードのリセット: すべてのユーザーに対してセルフサービスによるパスワードのリセットを使用する場合は、割り当てを調整して Microsoft マネージド デスクトップ サービス アカウントを除外します。 この割り当てを調整するには *、Microsoft* マネージド デスクトップ サービス アカウントを除くすべてのユーザーに対して Azure AD 動的グループを作成し、そのグループを "すべてのユーザー" ではなく割り当てに使用します。

サービス アカウントを検索して除外するために、使用できる動的クエリの例を次に示します。

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

このクエリでは、テナント ドメイン@TENANTを置き換える必要があります。



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップの使用を開始する手順

1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)
2. 登録後に設定を調整する (この記事)
3. [ライセンスを割り当てる](assign-licenses.md)
4. [Intune 会社ポータルを展開する](company-portal.md)
5. [Enterprise State Roaming を有効にする](enterprise-state-roaming.md)
6. [デバイスをセットアップする](set-up-devices.md)
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)
8. [アプリを展開する](deploy-apps.md)

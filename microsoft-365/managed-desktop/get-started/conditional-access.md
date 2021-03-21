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
ms.openlocfilehash: 760fcb94ec6d84a55fe4b8c3cb3540ae29994ae3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918444"
---
# <a name="adjust-settings-after-enrollment"></a>登録後に設定を調整する

Microsoft Managed Desktop への登録が完了したら、一部の管理設定を調整する必要がある場合があります。 必要に応じて確認および調整するには、次の手順を実行します。

1. 次のセクションで説明する Microsoft Intune と Azure Active Directory の設定を確認します。
2. 環境に適用される項目がある場合は、説明した調整を行います。
3. すべての設定が正しいか再確認する場合は、準備状況評価ツールを再実行[](https://aka.ms/mmdart)して、Microsoft Managed Desktop と何も競合しないか確認できます。

> [!NOTE]
> 操作が数か月後に続く場合、Microsoft 管理デスクトップに影響を与える Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーへの登録後に変更を加えた場合、Microsoft Managed Desktop が正常に動作しなくる可能性があります。 サービスの問題を回避するには、「準備状況評価ツールで見つかった[](../get-ready/readiness-assessment-fix.md)問題を修正する」で説明されている特定の設定を確認してから、そこに表示されているポリシーを変更します。 準備状況評価ツールをいつでも再実行することもできます。


## <a name="microsoft-intune-settings"></a>Microsoft Intune の設定

- Autopilot 展開プロファイル: 自動パイロット ポリシーを使用する場合は、各ポリシーを更新して、モダン **Workplace デバイス -All** Azure AD グループを除外します。 それらを更新するには、[割り当て] の[除外されたグループ] セクションで、Microsoft Managed Desktop の登録中に作成されたモダン ワークプレース デバイス **-all** Azure AD グループを選択します。 Microsoft Managed Desktop では、Autopilot プロファイルも作成され、名前に "モダン ワークプレース" (モダン ワークプレースの自動パイロット プロファイル) **が含されます**。 独自の Autopilot プロファイルを更新する場合は、Microsoft  Managed Desktop によって作成されたモダン Workplace **Autopilot** プロファイルからモダン ワークプレース デバイス **-All** Azure AD グループを除外しなことを確認してください。

- 条件付きアクセス ポリシー: Microsoft **Managed** Desktop の登録後に Azure AD、Microsoft Intune、または Microsoft Defender for Endpoint に関連する新しい条件付きアクセス ポリシーを作成する場合は、モダン ワークプレース サービス アカウント Azure AD グループを除外します。 手順については、「条件付き [アクセス: ユーザーとグループ」を参照してください](/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 Microsoft Managed Desktop は、これらのアカウントへのアクセスを制限するために、個別の条件付きアクセス ポリシーを維持します。 Microsoft Managed Desktop 条件付きアクセス ポリシー (**モダン ワーク** プレース – セキュア ワークステーション)を確認するには、Microsoft Endpoint Manager に移動し、[エンドポイント セキュリティ] の [条件付きアクセス]**に移動します**。 名前に "モダン ワークプレース" がAD Microsoft Managed Desktop によって作成された条件付きアクセス ポリシーを変更しない。

- 多要素認証: Microsoft Managed Desktop 登録後に Azure AD、Intune、または Microsoft Defender for Endpoint に関連する条件付きアクセス ポリシーで新しい多要素認証要件を作成する場合は、モダン ワークプレース サービス アカウント **Azure** AD グループを除外します。 手順については、「条件付き [アクセス: ユーザーとグループ」を参照してください](/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 Microsoft Managed Desktop は、このグループのメンバーへのアクセスを制限するために、個別の条件付きアクセス ポリシーを維持します。 Microsoft Managed Desktop 条件付きアクセス ポリシー (モダン ワークプレース **-)** を確認するには、Microsoft Endpoint Manager に移動し、[エンドポイント セキュリティ] の [条件付きアクセス]**に移動します**。 

- Windows 10 更新リング: 作成した Windows 10 更新リング ポリシーの場合は、モダン ワークプレース デバイス **-** すべての Azure AD グループを各ポリシーから除外します。 手順については、「更新リングの [作成と割り当て」を参照してください](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings)。 Microsoft Managed Desktop では、一部の更新リング ポリシーも作成され、そのすべてが名前に "モダン ワークプレース" があります (たとえば、モダン ワークプレース更新ポリシー **[Broad]**、Modern Workplace Update Policy **[Fast]**、Modern Workplace Update Policy **[First]、** およびモダン ワークプレース更新ポリシー **[Test]** など)。 独自のポリシーを更新する場合は、Microsoft Managed Desktop が作成したグループからモダン ワークプレース デバイス **-All** Azure AD グループを除外しなけことを確認してください。 


## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

セルフサービス パスワードのリセット: すべてのユーザーにセルフサービス パスワードリセットを使用する場合は、割り当てを調整して Microsoft Managed Desktop サービス アカウントを除外します。 この割り当てを調整するには *、Microsoft* Managed Desktop サービス アカウントを除くすべてのユーザーに対して Azure AD 動的グループを作成し、そのグループを "すべてのユーザー" ではなく割り当てに使用します。

サービス アカウントを見つけて除外するために、次に使用できる動的クエリの例を示します。

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

このクエリでは、テナント ドメイン@TENANTを置き換える必要があります。



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop の使用を開始する手順

1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)
2. 登録後に設定を調整する (この記事)
3. [ライセンスを割り当てる](assign-licenses.md)
4. [Intune 会社ポータルを展開する](company-portal.md)
5. [Enterprise State Roaming を有効にする](enterprise-state-roaming.md)
6. [デバイスをセットアップする](set-up-devices.md)
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)
8. [アプリを展開する](deploy-apps.md)
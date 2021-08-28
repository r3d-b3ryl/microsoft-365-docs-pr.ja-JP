---
title: 365 Windows PC セットアップの問題のトラブルシューティング
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
description: 365 Business Cloud PC のセットアップWindowsトラブルシューティングする方法について説明します。
ms.date: 08/13/2021
ms.openlocfilehash: 701d1ce3ae97836d6687050e16a176aad85e2995
ms.sourcegitcommit: 132b8dc316bcd4b456de33d6a30e90ca69b0f956
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598932"
---
# <a name="troubleshoot-windows-365-business-cloud-pc-setup-issues"></a>365 Windows PC セットアップの問題のトラブルシューティング

ユーザーに "セットアップに失敗しました" というエラーが表示される場合、またはライセンスを割り当て後にセットアップに 90 分以上かかる場合は、この記事の手順を使用して問題を解決してください。

> [!IMPORTANT]
> この記事で説明されているほとんどのタスクを実行するには、グローバル管理者である必要があります。 他の管理者ロールを特定の手順に使用できる場合は、プロシージャの前に表示されます。 Azure portal の一部にログインまたはアクセスする権限を持ってない場合は、IT 管理者に問い合わせください。Azure ルールの詳細については [、「Azure AD組み込みロール」を参照してください](/azure/active-directory/roles/permissions-reference)。 Azure portal の詳細については、「Azure portal の [概要」を参照してください](/azure/azure-portal/azure-portal-overview)。

## <a name="step-1-verify-azure-ad-device-settings"></a>手順 1. Azure のデバイスADを確認する

[すべて **] に設定されている場合は、ユーザーがデバイス** を Azure AD参加 **できます。**

1. でポータルにサインインMicrosoft Azureします [https://portal.azure.com/](https://go.microsoft.com/fwlink/p/?linkid=516942) 。
2. [ビュー **の管理Azure Active Directory]** で、[表示]**を選択します**。
3. 左側のナビゲーションの [管理] で **、[デバイス**] を選択 **し**、[デバイス設定] **を選択します**。
4. ユーザー **が Azure デバイスにデバイス** を参加ADに設定されていない場合は、[すべて]を選択し、[保存] を **選択します**。
5. 手順[2 に進みます。365 BPRT Windowsシステム アカウントがアクティブな状態を確認します](#step-2-verify-that-the-windows-365-bprt-permanent-user-system-account-is-active)。

## <a name="step-2-verify-that-the-windows-365-bprt-permanent-user-system-account-is-active"></a>手順 2。 365 BPRT Windowsシステム アカウントがアクティブな状態を確認する

Windows 365 ライセンスが組織で初めて割り当てられると **、Windows 365 BPRT 常設** ユーザーというシステム アカウントが Azure AD で自動的に作成されます。 このアカウントを削除したり、アカウントに変更を加え (名前や UPN の変更など) したりしない。 システム アカウントが変更または削除された場合、セットアップは失敗します。 このシステム アカウントは、スムーズなセットアップ プロセスを保証し、Windows 365 Business のスコープサービス機能を超えて、書き込み機能や組織へのアクセス権を持たなかったりします。 このシステム アカウントを削除または変更する場合は、Windows 365 Business ライセンスを持つアカウントを使用して windows365.microsoft.com にログインし、トークンが更新するまで 12 時間待機する必要があります。

Azure Windows 365 BPRT 常設ユーザー システム アカウントがアクティブAD、次の手順を実行します。

1. Azure portal で、[概要] ページAzure Active Directory<a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">移動</a>します。
2. 左側のナビゲーションの [管理] で **、[ユーザー**] を **選択します**。
3. 検索ボックスに **「365 BPRT Windowsユーザー**」と入力し、Enter キーを **押します**。
4. 365 BPRT Windowsシステム アカウントが存在する場合は、手順[3 に進みます。デバイス ベースの MFA がオフになっていることを確認します](#step-3-verify-that-device-based-mfa-is-turned-off)。
5. Windows 365 BPRT 常設ユーザー システム アカウントが見つからない場合、または変更が行われた場合は、Windows 365 Business ライセンスが割り当てられているアカウントで windows365.microsoft.com にログインします。 新しいWindows 365 BPRT 常設ユーザーは 12 時間以内に生成されます。 トークンが再生成された後、手順 [6 に直接移動します。クラウド PC をリセットします](#step-6-reset-your-cloud-pcs)。

## <a name="step-3-verify-that-device-based-mfa-is-turned-off"></a>手順 3. デバイス ベースの MFA がオフになっていることを確認する

組織が構成されている可能性があります。多要素認証 (MFA) は、Azure サーバーにデバイスを参加AD。 その場合は、この設定をオフにする必要があります。 Azure AD にデバイスを登録または参加するために多要素認証が必要な場合は、[いいえ] **に設定するには、次の** 手順を使用します。

1. Azure portal で、[概要] ページAzure Active Directory<a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">移動</a>します。
2. 左側のナビゲーションの [管理] で **、[デバイス**] を選択 **し**、[デバイス設定] **を選択します**。
3. **Azure デバイスを使用してデバイス** を登録または参加するために多要素認証が必要な場合は、[はいAD] を選択し、[保存] を **選択します**。
4. 手順 [4 に進みます。MFA でセットアップがブロックされるのを確認します](#step-4-make-sure-that-mfa-doesnt-block-setup)。

## <a name="step-4-make-sure-that-mfa-doesnt-block-setup"></a>手順 4. MFA でセットアップがブロックされるのを確認する

条件付きアクセスを含むAzure AD Premium P1ライセンスをお持ちない場合は、手順[5 に進みます。MDM 機関の構成が正しく設定されていることを確認します](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)。 サブスクリプションにサブスクリプションが含まれるかどうかが分からないAzure AD Premium P1、「どのサブスクリプションを持っていますか[」を参照してください。](../admin-overview/what-subscription-do-i-have.md)

条件付きアクセスを含む Azure AD Premium P1 ライセンスがある場合は、この記事の残りの手順を完了した後で、最初に Windows 365 ホーム ページにサインインするユーザーを 1 人 [https://windows365.microsoft.com](https://windows365.microsoft.com) 選択します。 その最初のユーザーに対して MFA 条件付きアクセス ポリシーが設定されている必要はありません。 MFA は、セットアップの試行中もオフの状態を維持する必要があります。 すべてのクラウド PC が組織全体で正常にセットアップされた後、このユーザーに対して MFA を有効にできます。 条件付きアクセス ポリシーの詳細については、「条件付きアクセスとは」[を参照Azure Active Directory。](/azure/active-directory/conditional-access/overview)

条件付きアクセス ポリシーを確認するには、次の手順を使用します。

1. Azure portal で、[条件付きアクセス ポリシー <a href="https://go.microsoft.com/fwlink/p/?linkid=2169290" target="_blank">] ページに移動</a> します。
2. ポリシーが一覧に表示されていない場合は、手順 [5 に進みます。MDM 機関の構成が正しく設定されていることを確認します](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)。
3. ページにポリシーが表示されている場合は、ポリシー名を選択します。
4. [アクセス制御 **] セクションの** **[Grant]** で、[0 コントロールが選択されている] と表示されている場合は、ポリシーリストに戻り、次のポリシーを選択します。 それ以外の場合は、手順 5 に進みます。
5. [アクセス制御 **] セクション** の **[Grant]** で、複数のコントロールが選択されている場合は、選択されている n つのコントロール **リンクを選択** します。
6. 右側のウィンドウで **、[多要素** 認証を要求する] が選択されている場合は、チェック ボックスをオフにして、[選択] ボタン **を選択** します。
   > [!TIP]
   > または、最初のユーザーをポリシーから除外できます。 これを行う方法については、「条件付きアクセス ポリシーから除外されたユーザーを管理 [する」を参照してください](/azure/active-directory/governance/conditional-access-exclusion)。
7. すべての条件付きアクセス ポリシーに対して MFA を削除するまで、手順 3 ~ 6 を繰り返します。
8. 手順 [5 に進みます。MDM 機関の構成が正しく設定されていることを確認します](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)。

## <a name="step-5-make-sure-mdm-authority-configuration-is-set-up-correctly"></a>手順 5.  MDM 機関の構成が正しく設定されていることを確認する

この記事の手順 1 ~ 4 に基づいて変更を行った場合、根本的な原因が解決される可能性があります。 問題が修正されたと確認するには、手順 [6 に進みます。クラウド PC をリセットします](#step-6-reset-your-cloud-pcs)。

手順 1 ~ 4 に変更を加えなかった場合は、環境内の MDM 機関の構成によってセットアップエラーが発生する可能性があります。 その場合は、クラウド PC の管理にアプリを使用するMicrosoft Intuneに応じて、2 つのパスを使用できます。

- クラウド PC で Microsoft Intune を使用する場合は、「パス A: モビリティ[(MDM](#path-a-use-microsoft-intune-to-manage-your-cloud-pcs)と MAM) の設定が正しく構成されていることを確認する」の手順に従います。
- クラウド PC の管理にMicrosoft Intune計画しない場合は、「パス B: 自動 MDM 登録をオフにする」の手順[に従います](#path-b-turn-off-automatic-mdm-enrollment)。

### <a name="path-a-use-microsoft-intune-to-manage-your-cloud-pcs"></a>パス A.クラウド Microsoft Intuneを管理するには、次のコマンドを使用します。

Microsoft Intune を既に使用している場合や、Windows 365 クラウド PC の管理に使用する予定がある場合は、Azure AD のモビリティ (MDM と **MAM)** の設定が正しく構成されていることを確認してください。

1. Azure portal で、[概要] ページAzure Active Directory<a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">移動</a>します。
2. 左側のナビゲーションの [管理]**で、[モビリティ**(MDM と **MAM)]****を** 選択し、[次のMicrosoft Intune。
3. [構成 **] ページの** **[MDM** ユーザー スコープ] の横にある [ **一部]** または [ **すべて**] を選択し、[保存] を **選択します**。
4. 左側のナビゲーションの [**管理] で、[モビリティ**(MDM と **MAM)]** を選択し、[登録] をMicrosoft Intuneし、**手順** 3 を繰り返します。

クラウド PC が割り当てられているユーザーには、Intune ライセンスが割り当てられている必要があります。 CloudPCBPRT システム アカウントに Intune ライセンスを割り当てる必要はない。

> [!IMPORTANT]
> ライセンスを割り当てるには、グローバル管理者またはライセンス管理者か、ライセンス権限を持つロールが必要です。

1. [管理センター [Microsoft エンドポイント マネージャーで、[](https://go.microsoft.com/fwlink/p/?linkid=2169290)ユーザー] [**すべてのユーザー]**  >  **を選択します**。
2. [すべての **ユーザー] リストで** 、ユーザーを選択します。
3. [ユーザー プロファイル] **ページで** 、[ライセンス] を **選択します**。
4. [ライセンス] **ページで** 、[割り当て] **を選択します**。
5. **Intune を検索し**、チェック ボックスをオンにして、[保存] を **選択します**。 これで、サービスを使用してデバイスを登録するために必要なアクセス許可がユーザー アカウントに付与されます。
6. 手順 [6 に進みます。クラウド PC をリセットします](#step-6-reset-your-cloud-pcs)。

### <a name="path-b-turn-off-automatic-mdm-enrollment"></a>パス B. MDM の自動登録をオフにする

クラウド PC の管理にMicrosoft Intuneしない場合は、MDM の自動登録をオフにする必要があります。

> [!IMPORTANT]
> MDM 管理者ではない場合は、IT 管理者に最初に相談せずに、次のいずれかの手順を使用しません。クラウド PC がセットアップされていない場合にのみ、次の手順に従います。 構成の変更は、管理環境に影響を与える可能性があります。 ヘルプが必要な場合は [、Intune のサポートにお問い合わせください](/mem/get-support)。

#### <a name="use-the-azure-ad-portal-to-turn-off-automatic-intune-enrollment"></a>Azure ADポータルを使用して Intune の自動登録をオフにする

1. Azure portal で、[概要] ページAzure Active Directory<a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">移動</a>します。
2. 左側のナビゲーションの [管理]**で、[モビリティ**(MDM と **MAM)]****を** 選択し、[次のMicrosoft Intune。
3. [構成 **] ページ** に、次の 2 つのいずれかを表示します。 サブスクリプションを使用している場合Azure AD Premium MDM ユーザー スコープの横にある **[なし**] を選択し、[保存] を **選択します**。 サブスクリプションがインストールされていない場合は、[無効Azure AD Premiumを選択 **します**。
4. 左側のナビゲーションの [**管理] で、[モビリティ**(MDM と **MAM)]** を選択し、[登録] をMicrosoft Intuneし、**手順** 3 を繰り返します。
5. 手順 [6 に進みます。クラウド PC をリセットします](#step-6-reset-your-cloud-pcs)。


## <a name="step-6-reset-your-cloud-pcs"></a>手順 6. クラウド PC のリセット

この記事のトラブルシューティング手順を完了したら、ユーザーはクラウド PC のセットアップを再起動する必要があります。 

手順 [3 を完了したばかりの場合。デバイス ベースの MFA が](#step-3-verify-that-device-based-mfa-is-turned-off)オフになっていることを確認し、変更が有効になってから続行するまで少なくとも 10 分待ちます。 MFA から除外したユーザーが[、365](https://windows365.microsoft.com)ホーム ページにサインインする最初のユーザー Windows確認します。

"セットアップに失敗しました" というエラーが表示されたクラウド PC ユーザー全員に、次の手順を使用してクラウド PC をリセットしてください。

1. [Windows [365](https://windows365.microsoft.com)ホーム ページで、[セットアップに失敗しました] 状態のクラウド PC の歯車アイコンを選択し、[リセット] を選択 **します**。 このアクションは、セットアップ プロセスを再起動します。
2. リセット後、"セットアップに失敗しました" というエラーが引き続き表示され、手順 [5 をスキップした場合。MDM 機関の構成が正しく設定されていることを確認](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)し、その手順を完了してから、もう一度 CloudPC をリセットします。 それ以外の場合は、左側のナビゲーションで [新しいサポート要求] **を選択して** サポート チケットを開きます。
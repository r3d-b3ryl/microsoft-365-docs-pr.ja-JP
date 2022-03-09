---
title: LTI Microsoft OneDrive Blackboard との統合
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: 新しい Blackboard 用ツールの相互運用性を使用して、割り当ての作成と採点、コース コンテンツの構築とキュレーション、ファイルMicrosoft OneDrive ラーニング共同作業を行います。
ms.openlocfilehash: 94e77181244bbf02115bd706e86751a9382b906b
ms.sourcegitcommit: a9266e4e7470e8c1e8afd31fef8d266f7849d781
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2022
ms.locfileid: "63406591"
---
# <a name="integrate-microsoft-onedrive-lti-with-blackboard"></a>LTI Microsoft OneDrive Blackboard との統合

LTI Microsoft OneDrive Blackboard との統合は、2 段階のプロセスです。 最初の手順では、Microsoft OneDrive LTI を Blackboard コース内で使用し、2 番目の手順は Blackboard のMicrosoft OneDriveオンになります。

> [!IMPORTANT]
> この統合を実行するユーザーは、Blackboard の管理者であり、そのテナントの管理者Microsoft 365必要があります。

## <a name="recommended-browser-settings"></a>推奨されるブラウザー設定

- Cookie は、ユーザーに対して許可Microsoft OneDrive。
- ポップアップは、ユーザーがブロックMicrosoft OneDrive。

> [!NOTE]
>
> - Cookie は Chrome ブラウザーのシークレット モードでは既定では許可されません。許可する必要があります。
> - Microsoft OneDrive LTI は、ブラウザーのプライベート モードMicrosoft Edgeします。 Cookie をブロックしていない (既定で許可されている) 必要があります。

## <a name="register-the-onedrive-lti-13-tool-in-blackboard"></a>Blackboard OneDrive LTI 1.3 ツールを登録する

1. Blackboard の管理者パネルで、[ **LTI ツール プロバイダー] を選択します**。
2.  **SelectRegister LTI 1.3 ツール**。
3. [クライアント ID] フィールドに、次の ID を入力またはコピーして貼り付けます。 ``78cd1b1c-ccbd-4318-9f90-22241f63b1f5``

  > [!NOTE]
  > このクライアント ID を追加すると、Blackboard で 2 つの異なる配置が構成されます。1 つは、コンテンツ マーケット、ブックとツール、リッチ テキスト エディターからツールにアクセスできる配置と、Ultra コースのオンライン コースの [コンテンツの追加] メニューからツールにアクセスできる配置です。

4. **[送信]** を選択します。
5. Tool  **Statusview**  のすべての事前設定を確認し、[ツールの状態] ラウンド ボタンが選択されている  **isApproved を確認します**。
6.  **InInstitution Policies,** select **the Role in course** and the **Name** checkboxes in the user fields to send. 他のすべてのユーザー フィールドは省略可能ですが、インストールの将来の証明に任せOneDriveです。
7. **グレード サービスへのアクセスを許可する**  **andAllow メンバーシップ サービス アクセス** は、現時点ではオプションですが、LTI ツールの今後の更新に必要になる場合があります。
8. 展開 **ID をコピーします**。 Microsoft LTI ツールを構成するために必要になります。
9. [送信] **ボタンを** 選択して終了します。

## <a name="configure-the-microsoft-lti-tool-to-work-with-blackboard"></a>Blackboard で動作する Microsoft LTI ツールの構成

1. [LTI 登録ポータルMicrosoft OneDriveサインインします](https://onedrivelti.microsoft.com/admin)。
2. [管理者の **同意] ボタンを** 選択し、アクセス許可を受け入れる。

> [!CAUTION]
> この手順を実行しない場合は、次の手順でエラーが発生し、エラーが発生すると、この手順を 1 時間実行できません。

3. [新しい **LTI テナントの作成] ボタンを選択** します。
4. [LTI 登録] ページで、[LTI コンシューマー プラットフォーム] ドロップダウンから [ **黒** 板] を選択し、[次へ] ボタン **を選択** します。
5. Blackboard **にツールを登録** している間にコピーした展開 ID を貼り付け、[次へ] を選択 **します**。
6. 変更を確認して保存します。 登録が成功すると、メッセージが表示されます。
7. 登録の詳細は、ホーム ページの **[LTI** テナントの表示] ボタンを選択して確認することもできます。

これらの手順を完了すると、[コース コンテンツ] ページの [プラス] メニューを使用OneDriveからドキュメントを開く事が可能です。

## <a name="recommended-content"></a>推奨されるコンテンツ

[Microsoft Integrations for Blackboard](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft)

[Microsoft Teamsクラスの統合](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft_Classes)

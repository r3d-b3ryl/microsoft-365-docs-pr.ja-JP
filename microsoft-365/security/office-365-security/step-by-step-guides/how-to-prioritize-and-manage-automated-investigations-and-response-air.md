---
title: 自動調査と応答 (AIR) の優先順位付けと管理方法。
description: アクション センターから直接 AIR アクションを分析して承認する手順を説明します。 アラートがトリガーされると、自動調査と応答 (AIR) によって組織内の脅威の影響範囲が決定され、推奨される修復アクションが提供されます。
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 234ce1ecb486c01b95c91aa51a0c5fd6b46e7a3c
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66994308"
---
# <a name="prioritize-and-manage-automated-investigations-and-response-air"></a>自動調査と応答 (AIR) の優先順位付けと管理

自動調査と対応 (AIR) により、セキュリティ運用チームの時間と労力が節約されます。

- アラートがトリガーされると、自動調査によって組織内の脅威の影響範囲が決定され、推奨される修復アクションが提供されます。
- セキュリティ チームは、AIR オートメーションを活用して手動捜索の必要性を減らすことで時間を節約できます。
- これらの調査では、ゼロ時間自動消去 (ZAP) やその他の修復によってクリーンアップされていないメールを特定できます。
- AIR 調査では、危険なメールボックス構成や侵害されたメールボックスを示す可能性があるメールボックスの構成も特定されます。

調査アクション (および調査) には、インシデント、*アラート**、または**アクション センター* を介して、Microsoft セキュリティ ポータルの複数のポイントからアクセスできます。 どの管理者が使用するかは、管理者が実行しているワークフローに基づいています。

## <a name="why-use-the-action-center-workflow"></a>アクション センター ワークフローを使用する理由

*Email &コラボレーション* コンテンツの自動調査によって、*悪意のある* アクションや *疑わしい* アクションなどの判定が行われると、特定の修復アクションが作成されます。 推奨される修復アクションは自動的には実行されません。 SecOps は、提案されたアクションを *承認* するために、各調査に移動する必要があります。 *アクション センター* では、保留中のすべてのアクションが集計され、迅速な承認が得られます。

## <a name="what-youll-need"></a>必要なもの

- Microsoft Defender for Office 365 プラン 2 以降 (E5 に付属)
- 十分なアクセス許可 (セキュリティ リーダー、セキュリティ操作、またはセキュリティ管理者、および [検索ロールと消去](../permissions-microsoft-365-security-center.md) ロール)

## <a name="steps-to-analyze-and-approve-air-actions-directly-from-the-action-center"></a>アクション センターから直接 AIR アクションを分析して承認する手順

1. [Microsoft 365 Defender ポータル](https://security.microsoft.com/action-center)に移動し、サインインします。
2. アクション センターが読み込まれたら、アクションを並べ替えるために列をクリックしてフィルター処理と優先順位を設定するか、 **フィルター** を押して *エンティティの種類* (特定の URL) やアクションの種類 (論理的なメールの削除など) などのフィルターを適用します。
3. アクションがクリックされるとポップアップが開きます。 これは、確認のために画面の右側に表示されます。
4. アクションが要求される理由の詳細については、ポップアップで **[調査ページを開く** ] を選択して、このアクションにリンクされている調査またはアラートの詳細を確認します。 (管理者は、[保留中のアクション] タブを選択して、調査ページに表示される *アクション* を承認することもできます)。
5. それ以外の場合は、[ **承認** ] を選択して、推奨されるアクションをアクション センターから直接実行します。
6. 不要と判断した場合は、アクションを拒否します。

## <a name="check-air-history"></a>AIR 履歴を確認する

1. [Microsoft 365 Defender ポータル](https://security.microsoft.com)に移動し、サインインします。
2. 左側のナビゲーション ウィンドウで、[ **Action & submissions** ] を展開し、[ **アクション センター**] をクリックします。
3. アクション センターが読み込まれたら、[ **履歴** ] タブを押します。
4. 必要に応じて、意思決定、アクションのソース、決定を行った管理者など、AIR の履歴を表示します。

## <a name="more-information"></a>詳細情報

[Microsoft 365 の自動調査の結果を表示する - Office 365 |Microsoft Docs](../air-view-investigation-results.md)

[[調査] ページで保留中のアクションを承認および拒否する方法について説明します](../air-review-approve-pending-completed-actions.md)

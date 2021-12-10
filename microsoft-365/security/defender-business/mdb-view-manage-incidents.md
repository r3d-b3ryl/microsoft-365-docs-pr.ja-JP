---
title: Microsoft Defender for Business でのインシデントの表示と管理
description: アラートの管理、脅威への&、デバイスの管理、修復アクションの確認を行う方法について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 4927d57d0e549c1cc5e15c427f9d28abbd3dd856
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375655"
---
# <a name="view-and-manage-incidents-in-microsoft-defender-for-business"></a>Microsoft Defender for Business でのインシデントの表示と管理

> [!IMPORTANT]
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 この記事には、Microsoft Defender for Business (プレビュー) に含まれていない一部の機能について説明する可能性があるオンライン コンテンツへのリンクが含まれています。

脅威が検出され、アラートがトリガーされると、インシデントが作成されます。 会社のセキュリティ チームは、ポータルでインシデントを表示およびMicrosoft 365 Defenderできます。

**この記事には、次の内容が含まれます**。

- [インシデントとアラートを監視する方法](#monitor-your-incidents--alerts)
- [アラートの重大度](#alert-severity)
- [次の手順](#next-steps)

## <a name="monitor-your-incidents--alerts"></a>インシデントとアラート&監視する

1. [ポータル( [https://security.microsoft.com](https://security.microsoft.com) Microsoft 365 Defender] のナビゲーション ウィンドウで、[インシデント]**を選択します**。 作成されたインシデントは、ページに一覧表示されます。

   :::image type="content" source="../../media/defender-business/mdb-incidents-list.png" alt-text="インシデント リストのスクリーンショット":::

2. アラートを選択して、そのフライアウト ウィンドウを開き、アラートの詳細を確認できます。 

   :::image type="content" source="../../media/defender-business/mdb-incident-flyout.png" alt-text="フライアウトが開いていると選択されたインシデントのスクリーンショット":::

3. フライアウト ウィンドウでは、アラート タイトルを表示したり、影響を受けたアセット (エンドポイントやユーザー アカウントなど) の一覧を表示したり、利用可能なアクションを実行したり、リンクを使用して詳細情報を表示したり、選択したアラートの詳細ページを開くなどの操作を行うことができます。 

> [!TIP]
> Microsoft Defender for Business は、推奨されるアクションを提供することで、検出された脅威に対処するために設計されています。 アラートを表示するときに、実行する推奨されるアクションを探します。 また、脅威の重大度だけでなく、会社のリスクレベルにも基づいて決定されるアラートの重大度に注意してください。 

## <a name="alert-severity"></a>アラートの重大度

検出Microsoft Defender ウイルス対策 (マルウェア) の絶対重大度と、個々のエンドポイントに潜在的なリスク (感染した場合) に基づいてアラートの重大度を割り当てる場合。
Microsoft Defender for Business は、検出された動作の重大度、実際のリスクをエンドポイント (デバイス) に割り当て、さらに重要なことに、企業に潜在的なリスクを割り当てします。 次の表に、いくつかの例を示します。 <br/><br/>

| シナリオ | アラートの重大度 | 理由 |
|:---|:---|:---|
| Microsoft Defender ウイルス対策脅威を検出して停止してから、損害を与える可能性があります。 | 情報 | 脅威は、損害が発生する前に停止されました。 |
| Microsoft Defender ウイルス対策内で実行していたマルウェアを検出します。 マルウェアが停止して修復されます。 | 低い | 個々のエンドポイントに対して一部の損害が発生した可能性があるが、マルウェアが企業に脅威を与える可能性はありません。 |
| 実行中のマルウェアは、Microsoft Defender for Business によって検出されます。 マルウェアはほぼ即座にブロックされます。 | 中または高 | マルウェアは、個々のエンドポイントと企業に脅威を与える。 |
| 疑わしい動作は検出されますが、修復アクションはまだ実行されません。 | 低、中、高 | 重大度は、動作が企業に脅威を与える度合いによって異なります。 |

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business での脅威への対応と軽減](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)

- [Microsoft Defender for Business でデバイス ポリシーを表示または編集する](mdb-view-edit-policies.md)
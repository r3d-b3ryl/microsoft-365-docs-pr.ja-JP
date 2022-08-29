---
title: Microsoft Defender for Businessでのインシデントの表示と管理
description: Defender for Business で、アラートの表示と管理、脅威への対応、デバイスの管理、検出された脅威に対する修復アクションの確認を行います。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 2c751289c9d365d72909433fe6534f3f00ba3638
ms.sourcegitcommit: 9b10e56b9e83f3a80757fa6108bebd1d80cf4178
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67320418"
---
# <a name="view-and-manage-incidents-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでのインシデントの表示と管理

脅威が検出されアラートがトリガーされると、インシデントが作成されます。 会社のセキュリティ チームは、Microsoft 365 Defender ポータルでインシデントを表示および管理できます。

**この記事には次のものが含まれます**。

- [インシデントとアラートを監視する方法](#monitor-your-incidents--alerts)
- [アラートの重大度](#alert-severity)
- [次の手順](#next-steps)


## <a name="monitor-your-incidents--alerts"></a>アラート&インシデントを監視する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで、[**インシデント**] を選択します。 作成されたすべてのインシデントがページに表示されます。

   :::image type="content" source="../../media/defender-business/mdb-incidents-list.png" alt-text="インシデントの一覧のスクリーンショット":::

2. アラートを選択してポップアップ ウィンドウを開き、アラートの詳細を確認できます。 

   :::image type="content" source="../../media/defender-business/mdb-incident-flyout.png" alt-text="ポップアップを開いた状態で選択されたインシデントのスクリーンショット":::

3. ポップアップ ウィンドウには、アラート のタイトルを表示したり、影響を受けた資産の一覧 (エンドポイントやユーザー アカウントなど) を表示したり、使用可能なアクションを実行したり、リンクを使用して詳細情報を表示したり、選択したアラートの詳細ページを開いたりすることもできます。 

> [!TIP]
> Defender for Business は、推奨されるアクションを提供することで、検出された脅威に対処できるように設計されています。 アラートを表示するときは、推奨されるアクションを探します。 また、アラートの重大度もメモします。これは、脅威の重大度だけでなく、会社に対するリスクのレベルにも基づいて決定されます。 

## <a name="alert-severity"></a>アラートの重大度

Microsoft Defender ウイルス対策が、検出された脅威 (マルウェア) の絶対重大度と個々のエンドポイント (感染した場合) に潜在的なリスクに基づいてアラートの重大度を割り当てる場合。 Defender for Business は、検出された動作の重大度、エンドポイント (デバイス) に対する実際のリスク、さらに重要なのは、潜在的なリスクに基づいて、アラートの重大度を会社に割り当てます。 次の表に、いくつかの例を示します。

| シナリオ | アラートの重大度と理由 |
|:---|:---|
| Microsoft Defender ウイルス対策では、脅威が検出され、被害が発生する前に停止します。 | **情報。** 脅威は、被害が発生する前に停止されました。 |
| Microsoft Defender ウイルス対策は、社内で実行されていたマルウェアを検出します。 マルウェアが停止され、修復されます。 | **低** 。 個々のエンドポイントに対して一部の被害が発生した可能性がありますが、マルウェアは会社に脅威を与える必要はありません。 |
| Defender for Business によって、実行中のマルウェアが検出されます。 マルウェアはほぼ即座にブロックされます。 | **中** または **高**。 マルウェアは、個々のエンドポイントと会社に脅威を与えています。 |
| 疑わしい動作は検出されますが、修復アクションはまだ実行されません。 | **低**、 **中**、または **高**。 重大度は、その動作が会社に脅威を与える度合いによって異なります。 |

## <a name="next-steps"></a>次の手順

- [Defender for Business の脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)
- [Defender for Business でデバイス ポリシーを表示または編集する](mdb-view-edit-policies.md)
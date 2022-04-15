---
title: Microsoft Defender for Businessでのインシデントの表示と管理
description: アラートの管理、脅威への対応、デバイスの管理、修復アクションの確認&表示する方法について説明します
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 04/12/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: ec1d85b72cfbe17e182d3aed573476e4fadfdef6
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2022
ms.locfileid: "64861446"
---
# <a name="view-and-manage-incidents-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでのインシデントの表示と管理

> [!NOTE]
> Microsoft Defender for Businessが[Microsoft 365 Business Premium](../../business-premium/index.md)に含まれるようになりました。 

脅威が検出され、アラートがトリガーされると、インシデントが作成されます。 会社のセキュリティ チームは、Microsoft 365 Defender ポータルでインシデントを表示および管理できます。

**この記事には次のものが含まれます**。

- [インシデントとアラートを監視する方法](#monitor-your-incidents--alerts)
- [アラートの重大度](#alert-severity)
- [次の手順](#next-steps)

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="monitor-your-incidents--alerts"></a>アラート&インシデントを監視する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで、[**インシデント**] を選択します。 作成されたすべてのインシデントがページに表示されます。

   :::image type="content" source="../../media/defender-business/mdb-incidents-list.png" alt-text="インシデントの一覧のスクリーンショット":::

2. アラートを選択してポップアップ ウィンドウを開き、アラートの詳細を確認できます。 

   :::image type="content" source="../../media/defender-business/mdb-incident-flyout.png" alt-text="ポップアップを開いた状態で選択されたインシデントのスクリーンショット":::

3. ポップアップ ウィンドウには、アラート のタイトルを表示したり、影響を受けた資産の一覧 (エンドポイントやユーザー アカウントなど) を表示したり、使用可能なアクションを実行したり、リンクを使用して詳細情報を表示したり、選択したアラートの詳細ページを開いたりすることもできます。 

> [!TIP]
> Microsoft Defender for Businessは、推奨されるアクションを提供することで、検出された脅威に対処できるように設計されています。 アラートを表示するときは、推奨されるアクションを探します。 また、アラートの重大度もメモします。これは、脅威の重大度だけでなく、会社に対するリスクのレベルにも基づいて決定されます。 

## <a name="alert-severity"></a>アラートの重大度

検出された脅威 (マルウェア) の絶対重大度と個々のエンドポイント (感染した場合) に潜在的なリスクに基づいてアラートの重大度を割り当てるMicrosoft Defender ウイルス対策。
Microsoft Defender for Businessは、検出された動作の重大度、エンドポイント (デバイス) への実際のリスク、さらに重要なのは、潜在的なリスクに基づいて、アラートの重大度を会社に割り当てます。 次の表に、いくつかの例を示します。

| シナリオ | アラートの重大度 | 理由 |
|:---|:---|:---|
| Microsoft Defender ウイルス対策は、脅威が何らかの損害を与える前に、脅威を検出して停止します。 | 情報 | 脅威は、被害が発生する前に停止されました。 |
| Microsoft Defender ウイルス対策社内で実行されていたマルウェアを検出します。 マルウェアが停止され、修復されます。 | 低 | 個々のエンドポイントに対して一部の被害が発生した可能性がありますが、マルウェアは会社に脅威を与える必要はありません。 |
| 実行中のマルウェアは、Microsoft Defender for Businessによって検出されます。 マルウェアはほぼ即座にブロックされます。 | 中または高 | マルウェアは、個々のエンドポイントと会社に脅威を与えています。 |
| 疑わしい動作は検出されますが、修復アクションはまだ実行されません。 | 低、中、または高 | 重大度は、その動作が会社に脅威を与える度合いによって異なります。 |

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Businessの脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)
- [Microsoft Defender for Businessでデバイス ポリシーを表示または編集する](mdb-view-edit-policies.md)
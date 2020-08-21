---
title: 時間のかかるメール フロー ルールの修正のインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターの低速メール フロー ルールのインサイトを使用して、組織の不効率な、または壊れていないメール フロー ルール (トランスポート ルールとも呼ばれる) を特定して修正する方法を学習できます。
ms.openlocfilehash: 6319633c47e34d7b62c4f68bfbda7fe298c0deb3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826883"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターの低速メール フローのルールのインサイト&を修正する

効率のないメール フロー ルール (トランスポート ルールとも呼ばれる) は、組織のメール フローの遅延につながる可能性があります。 この分析情報は、組織のメール フローに影響を与えるメール フロー ルールを報告します。 たとえば、次のような種類のルールがあります。

- 大規模なグループ **のメンバーとして使用** する条件。
- 複雑な正規表現 (regex) パターン マッチングを使用する条件。
- 添付ファイルでコンテンツ チェックを使用する条件。

セキュリティ &/コンプライアンス[Mail flow dashboard](mail-flow-insights-v2.md)**センターの [メール フロー]** ダッシュボードの [推奨**される**ユーザーに対しては、転送処理の低下に関するルール] の見出しの分析情報を参照してください。メール フロー ルールの処理が完了しきれい時間がかかりすぎています。 この分析情報は、条件が検出された後にのみ表示されます (メール ループがない場合、分析情報は表示されません)。

この通知を使うと、メール フローの遅延を減らすメール フロー ルールを識別して詳細に変更することができます。

![メール フロー ダッシュボードの [推奨されるユーザーの詳細] 領域の低速メール フロー ルールの分析情報を修正する](../../media/mfi-fix-slow-mail-flow-rules.png)

ウィジェ **ットの [** 詳細の表示] をクリックすると、さらに情報を含むポップアップが表示されます。

- **ルール**: 概要に上にリンクすると、ルールのすべての条件、例外、アクションを表示できます。 概要をクリックすると、Exchange 管理センター (EAC) でルールを編集できます。
- **評価されるメッセージ数**: [サンプル メッセージ **の表示** ] をクリックすると [、ルールの](message-trace-scc.md) 影響を受けったメッセージのサンプルのメッセージ トレース結果を確認できます。
- **各メッセージの平均時間**
- **メッセージに使った中央**管理時間: 上半分と下半分のデータを区切る中央値。

![[フライト の低速メール フロー ルール] の見出しをクリックした後に表示される詳細ポップアップ](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Exchange Online 内のメール フロー ルールの条件と例外の詳細については、Exchange Online 内のメール フロー ルール [の条件と例外 (述語) を参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

## <a name="related-topics"></a>関連トピック

メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。

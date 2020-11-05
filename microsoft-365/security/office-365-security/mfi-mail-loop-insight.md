---
title: メール ループの可能性の修正のインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある考えられるメールループの洞察を使用して、組織内のメールループを特定して修正する方法について説明します。
ms.openlocfilehash: 1d49fd93b2ea068986e003b36077672215a2dd57
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920569"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターで使用可能なメールループの洞察を修正する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


次の理由により、メールループが正しくありません。

- システムリソースが浪費されます。
- 組織のメールボリュームクォータを消費します。
- 送信者は、元のメッセージの送信者に、わかりづらい配信不能レポート (Ndr またはバウンスメッセージとも呼ばれます) を送信します。

[セキュリティ & コンプライアンスセンター](https://protection.office.com)の [メールフローダッシュボード](mail-flow-insights-v2.md)の [お客様 **に推奨** されるメールループ] 領域で、組織内でメールループが検出されたときに通知する **メールループを修正** します。

この洞察は、条件が検出された後にのみ表示されます (メールループがない場合は、洞察は見られません)。

![メールフローダッシュボードのお住まいの地域で推奨されるメールフロールールの詳細を修正する](../../media/mfi-fix-possible-mail-loop.png)

ウィジェットの [ **詳細の表示** ] をクリックすると、詳細情報を含むフライアウトが表示されます。

- **ドメイン**
- **メッセージ数** : [ **サンプルメッセージの表示** ] をクリックすると、ループの影響を受けたメッセージのサンプルの [追跡](message-trace-scc.md) 結果が表示されます。
- **ドメインの種類** 。たとえば、権限のある、または権限がない。
- **Mx レコード** : ドメインの mx レコードのホスト ( **メールサーバー** ) と **優先度** の値。
- **ループの理由** と **解決方法** : 最も一般的なメールループシナリオを特定し、そのループを解決するために推奨されるアクションを提供します。

![考えられるメールループの状況を修正する [詳細の表示] をクリックした後に表示される詳細ポップアップ](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>関連項目

メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。

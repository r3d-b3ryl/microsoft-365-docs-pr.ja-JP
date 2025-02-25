---
title: Microsoft Defender for Office 365の調査における電子メール分析
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 自動インシデント対応、調査、修復、脅威保護
description: 調査の電子メール分析がMicrosoft Defender for Office 365でどのように機能するかを確認します。
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 49a244e948da14e328ab3db64dc495ab6e5d6dd4
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468019"
---
# <a name="email-analysis-in-investigations-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365の調査における電子メール分析

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

アラートの自動調査中に、Microsoft Defender for Office 365は元のメールの脅威を分析し、元の電子メールに関連するその他の電子メールを識別し、攻撃の一部である可能性があります。 この分析は、電子メール攻撃が 1 つの電子メールで構成されることはほとんどないため、重要です。

自動調査の電子メール分析では、元の電子メールの属性を使用して、組織によって送受信された電子メールのクエリを実行する電子メール クラスターを識別します。 これは、アナリストがエクスプローラーまたは Advanced Hunting で関連するメールを探すセキュリティ運用アナリストに似ています。 攻撃者は通常、セキュリティ検出を回避するために電子メール パラメーターをモーフィングするため、一致するメールを識別するためにいくつかのクエリが使用されます。 クラスタリング分析では、次のチェックを実行して、調査に関連する電子メールを処理する方法を決定します。

- 電子メール分析では、元のメールからの属性 (送信者の値 (IP アドレス、送信ドメイン) とコンテンツ (件名、クラスター ID) を使用して、電子メールのクエリ (クラスター) を作成して、関連する電子メールを検索します。
- 元の電子メールの URL とファイルの分析で、悪意のあるもの (マルウェアやフィッシング) が検出された場合は、悪意のある URL またはファイルを含むメールのクエリまたはクラスターも作成されます。
- 電子メール クラスタリング分析では、クラスター内の一致する電子メールに関連付けられている脅威をカウントして、電子メールが悪意のある、疑わしい、または明確な脅威がないかどうかを判断します。 クエリに一致する電子メールのクラスターに、スパム、通常のフィッシング、高信頼のフィッシング、マルウェアの脅威が十分に存在する場合、電子メール クラスターはその脅威の種類をそれに適用します。
- 電子メール クラスタリング分析では、電子メール クラスター内の元の電子メールと電子メールの最新の配信場所もチェックされ、電子メールがまだ削除が必要な可能性があるか、既に修復または防止されているかどうかを特定するのに役立ちます。 攻撃者が悪意のあるコンテンツをモーフィングし、セキュリティ ポリシーと保護がメールボックス間で異なる可能性があるため、この分析は重要です。 この機能により、1 つ以上の悪意のあるメールが検出され、ゼロ時間の自動消去 (ZAP) によって削除されたにもかかわらず、悪意のあるコンテンツがメールボックスに残る可能性がある状況につながります。
- マルウェア、信頼度の高いフィッシング、悪意のあるファイル、または悪意のある URL の脅威により悪意があると見なされる電子メール クラスターは、クラウド メールボックス (受信トレイまたは迷惑メール フォルダー) にまだ存在する場合にメールを論理的に削除するための保留中のアクションを取得します。 悪意のある電子メールまたは電子メール クラスターが、クラウド メールボックス内に存在しない "メールボックス内" (ブロック、検疫、失敗、論理的な削除など) または "オンプレミス/外部" のみである場合、保留中のアクションは設定されません。
- いずれかの電子メール クラスターが悪意があると判断された場合、クラスターによって識別された脅威は、調査に関連する元の電子メールに適用されます。 この動作は、一致する電子メールに基づいて元の電子メールの判定を決定するために、電子メールハンティング結果を使用するセキュリティ運用アナリストに似ています。 この結果により、元の電子メールの URL、ファイル、またはソース 電子メール インジケーターが検出されたかどうかに関係なく、システムは、パーソナル化、モーフィング、回避、またはその他の攻撃者の手法によって検出を回避する可能性のある悪意のある電子メールを識別できます。
- ユーザー侵害の調査では、メールボックスによって作成された潜在的な電子メールの問題を特定するために、追加の電子メール クラスターが作成されます。 このプロセスには、クリーンな電子メール クラスター (ユーザーからの適切なメール、潜在的なデータ流出、潜在的なコマンド/制御メール)、疑わしい電子メール クラスター (スパムまたは通常のフィッシングを含む電子メール)、悪意のある電子メール クラスター (マルウェアや高信頼フィッシングを含むメール) が含まれます。 これらの電子メール クラスターは、セキュリティ運用アナリストデータを提供して、侵害から対処する必要があるその他の問題と、元のアラートをトリガーした可能性のある電子メールの可視性 (ユーザー送信制限をトリガーしたフィッシングやスパムなど) を決定します。

類似度と悪意のあるエンティティ クエリを使用した電子メール クラスタリング分析により、攻撃からのメールが 1 つだけ識別された場合でも、電子メールの問題が完全に特定され、クリーンアップされます。 電子メール クラスターの詳細サイド パネル ビューからのリンクを使用して、エクスプローラーまたは Advanced Hunting でクエリを開き、詳細な分析を実行し、必要に応じてクエリを変更できます。 この機能を使用すると、電子メール クラスターのクエリが狭すぎる、または広すぎる (無関係のメールを含む) 場合は、手動での絞り込みと修復が可能になります。

調査における電子メール分析のその他の機能強化を次に示します。

## <a name="air-investigation-ignores-advanced-delivery-items-secops-mailbox-and-phishedu-messages"></a>AIR 調査では、高度な配信項目が無視されます (SecOps メールボックスとフィッシングEDU メッセージ)

電子メール クラスタリング分析中、すべてのクラスタリング クエリは、高度な配信ポリシーで Security Operations メールボックスとして設定されたセキュリティ メールボックスを無視します。 同様に、電子メール クラスタリング クエリでは、Advanced Delivery ポリシーで構成されているフィッシング シミュレーション (教育機関) メッセージは無視されます。 クラスタリング属性をよりシンプルで読みやすくするために、SecOps と PhishEdu の除外値はどちらもクエリに表示されません。 この除外により、脅威インテリジェンスと運用メールボックス (SecOps メールボックス) とフィッシング シミュレーション (PhishEdu) が脅威分析中に無視され、修復中に削除されることはありません。

>[!Note]
>電子メール クラスターを開いてエクスプローラーで電子メール クラスターの詳細を表示すると、Explorer でフィッシング詐欺と SecOps メールボックス フィルターが適用されますが、表示されません。 エクスプローラーのフィルター、日付、またはページ内のクエリを更新すると、PhishEdu/SecOps フィルターの除外が削除され、これらと一致する電子メールが再び表示されます。 ブラウザーの更新機能を使用してエクスプローラー ページを更新すると、元のクエリ フィルターが再読み込み (フィッシング/SecOps フィルターを含む) になりますが、以降の変更は削除されます。
>

## <a name="air-updates-pending-email-action-status"></a>AIR の更新保留中の電子メール アクションの状態

調査電子メール分析では、調査の証拠とアクションを作成するために、調査時の電子メールの脅威と場所が計算されます。 調査外のアクションが調査に関連する電子メールに影響を与えると、このデータは古くなったり古くなったりする可能性があります。 たとえば、セキュリティ操作による手動の捜索と修復では、調査に含まれる電子メールがクリーンアップされる場合があります。 同様に、並行調査で承認された削除アクションやゼロ時間自動消去 (ZAP) 自動検疫アクションによって電子メールが削除された可能性があります。 さらに、電子メール配信後の脅威の検出が遅延すると、調査の電子メール クエリ/クラスターに含まれる脅威の数が変更される可能性があります。

調査アクションを最新の状態に保つには、保留中のアクションを含む調査は定期的に電子メール分析クエリを再実行して、電子メールの場所と脅威を更新します。

- 電子メール クラスターデータが変更されると、脅威と最新の配信場所の数が更新されます。
- 保留中のアクションを含む電子メールまたは電子メール クラスターがメールボックスに存在しなくなった場合、保留中のアクションは取り消され、悪意のある電子メール/クラスターは修復されたと見なされます。
- 上記のようにすべての調査の脅威が修復または取り消されると、調査は修復された状態に移行し、元のアラートは解決されます。

## <a name="the-display-of-incident-evidence-for-email-and-email-clusters"></a>電子メール クラスターと電子メール クラスターのインシデント証拠の表示

インシデントの [ **証拠と対応** ] タブの電子メール ベースの証拠に、次の情報が表示されるようになりました。

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example.png" alt-text="証拠と応答の電子メール分析情報" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example.png":::

図の番号付き吹き出しから:

1. **アクション センター** に加えて、修復アクションを実行できます。
2. **悪意のある** 判定 (**ただし疑わしい**) を使用して、電子メール クラスターの修復アクションを実行できます。
3. 電子メールスパムの判定では、フィッシングは高い信頼度と通常のフィッシングに分割されます。

   悪意のある判定の場合、脅威カテゴリはマルウェア、高信頼フィッシング、悪意のある URL、悪意のあるファイルです。

   疑わしい判定の場合、脅威カテゴリはスパムと通常のフィッシングです。

4. 電子メール数は最新の配信場所に基づいており、メールボックス内ではなく、オンプレミスのメールボックス内の電子メールのカウンターが含まれます。
5. 最新のデータに対して更新される可能性があるクエリの日付と時刻が含まれます。

インシデントの [ **エンティティ]** タブの電子メール クラスターまたは電子メール クラスターの場合、[ **防止]** は、このアイテム (メールまたはクラスター) のメールボックスに悪意のある電子メールが存在しなかったことを意味します。 次に例を示します。

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png" alt-text="禁止された電子メール。" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png":::

この例では、電子メールは悪意がありますが、メールボックスには含まれません。

## <a name="next-steps"></a>次の手順

- [保留中または完了した修復アクションを表示する](air-review-approve-pending-completed-actions.md)

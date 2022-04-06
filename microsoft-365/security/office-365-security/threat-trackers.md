---
title: '脅威トラッカー - 新機能とNoteworthy 機能 '
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: a097f5ca-eac0-44a4-bbce-365f35b79ed1
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: 新しい注目のトラッカーを含む脅威トラッカーについて学び、組織がセキュリティ上の懸念事項を把握するのに役立ちます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ba038f94e711470242995a8ea0f082cd6d82dcda
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663250"
---
# <a name="threat-trackers---new-and-noteworthy"></a>脅威トラッカー - 新機能とNoteworthy 機能 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Office 365脅威の調査と対応](office-365-ti.md)機能により、組織のセキュリティ チームはサイバーセキュリティの脅威を検出して対処できます。 Office 365脅威の調査と対応機能には、注目に値するトラッカーを含む脅威トラッカー機能が含まれます。 これらの新機能と次の手順の概要については、この記事を参照してください。

> [!IMPORTANT]
> Office 365脅威インテリジェンスは、追加の脅威保護機能と共に、プラン 2 Microsoft Defender for Office 365になりました。 詳細については、「[Microsoft Defender for Office 365プランと価格」と](https://products.office.com/exchange/advance-threat-protection)[「Microsoft Defender for Office 365サービスの説明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。

## <a name="what-are-threat-trackers"></a>脅威トラッカーとは

脅威トラッカーは、会社に影響を与える可能性があるさまざまなサイバーセキュリティの問題に関するインテリジェンスを提供する有益なウィジェットとビューです。 たとえば、脅威トラッカーを使用して、マルウェア キャンペーンの傾向に関する情報を表示できます。

:::image type="content" source="../../media/a883b5ac-8e2b-469a-90e0-f8ad39bb63b7.png" alt-text="マルウェア キャンペーンを示す脅威トラッカーの例" lightbox="../../media/a883b5ac-8e2b-469a-90e0-f8ad39bb63b7.png":::

ほとんどのトラッカー ページには、定期的に更新される傾向のある数値、最も大きい問題または最も大きくなった問題を理解するのに役立つウィジェット、エクスプローラーに移動する **アクション** 列のクイック リンクが含まれており、詳細な情報を表示できます。

:::image type="content" source="../../media/e426f220-fdcb-4dd9-99a2-db97dbcf71d5.png" alt-text="エクスプローラーのキャンペーン情報の例" lightbox="../../media/e426f220-fdcb-4dd9-99a2-db97dbcf71d5.png":::

トラッカーは、Microsoft Defender for Office 365プラン 2 で得られる多くの優れた機能の[ほんの一部です](office-365-ti.md)。 脅威トラッカーには、 [注目に値するトラッカー](#noteworthy-trackers)、 [Trending トラッカー](#trending-trackers)、 [追跡済みクエリ](#tracked-queries)、保存済み [クエリが含まれます](#saved-queries)。

組織の脅威トラッカーを表示して使用するには、Microsoft 365 Defender ポータル<https://security.microsoft.com>を開き、[**Email & コラボレーション** \> **脅威トラッカー**] に移動します。 **脅威トラッカー** ページに直接移動するには、<https://security.microsoft.com/threattrackerv2>.

> [!NOTE]
> Threat Trackers を使用するには、グローバル管理者、セキュリティ管理者、またはセキュリティ リーダーである必要があります。 [Microsoft 365 Defender ポータルのアクセス許可に関するページを](permissions-microsoft-365-security-center.md)参照してください。

### <a name="noteworthy-trackers"></a>注目に値するトラッカー

注目に値するトラッカーは、大小の脅威とリスクについて知っておく必要があると思われる場所です。 注目に値するトラッカーは、これらの問題がMicrosoft 365環境に存在するかどうかを確認するのに役立ちます。また、何が起こっているか、組織のOffice 365の使用にどのような影響を与えるかについて詳しく説明する記事 (この記事など) へのリンクも役立ちます。 大きな新しい脅威 (Wannacry、Petya など) でも、(他の注目に値する他のアイテムである Nemucod など) 新しい課題を生み出す可能性のある既存の脅威であっても、ここで重要な新しいアイテムを見つけることができます。セキュリティ チームは定期的に確認して確認する必要があります。

通常、新しい脅威を特定し、この機能が提供する余分な可視性が必要になる可能性があると考えられる場合、注目に値するトラッカーは数週間だけ投稿されます。 脅威の最大のリスクが過ぎたら、その注目すべき項目を削除します。 これにより、リストを最新の状態に保ち、関連する他の新しいアイテムを最新の状態に保つことができます。

### <a name="trending-trackers"></a>Trending Trackers

トレンドトラッカー (旧称キャンペーン) は、過去 1 週間に組織の電子メールで受信した新しい脅威を強調表示します。 Trending Trackers ビューでは、組織のOffice 365環境に影響を与える電子メールの脅威の動的な評価が提供されます。 このビューは、テナント レベルのマルウェアの傾向を示し、増加、フラット、または減少しているマルウェア ファミリを特定し、脅威にさらに注意が必要な詳細な分析情報を管理者に提供します。

:::image type="content" source="../../media/d2ccc1a0-2a1d-4e36-99b5-6766c207772f.png" alt-text="マルウェア キャンペーンウィジェットの傾向の例" lightbox="../../media/d2ccc1a0-2a1d-4e36-99b5-6766c207772f.png":::

トレンドトラッカーを使用すると、より広範な企業環境が攻撃に対して確実に準備されるように、新しい脅威を確認する必要があります。

### <a name="tracked-queries"></a>追跡されたクエリ

追跡されたクエリでは、保存したクエリを利用して、組織内のMicrosoft 365アクティビティを定期的に評価します。 これにより、イベントの傾向が得られるので、今後数か月でさらに多くのイベントが発生します。 追跡されたクエリは自動的に実行され、クエリの再実行を忘れずに最新の情報が得られます。

:::image type="content" source="../../media/0c556174-06eb-4ae5-b32a-5ff76b9e4f13.png" alt-text="1 つを選択した追跡クエリの例" lightbox="../../media/0c556174-06eb-4ae5-b32a-5ff76b9e4f13.png":::

### <a name="saved-queries"></a>保存されたクエリ

保存されたクエリは、[トラッカー] セクションにも表示されます。 保存されたクエリを使用すると、検索を毎回再作成することなく、すばやく繰り返し検索に戻す一般的なエクスプローラー検索を格納できます。

:::image type="content" source="../../media/188cf3ff-58f1-41ea-81aa-76158d8f40c3.png" alt-text="1 つを選択して追跡されたクエリの一覧" lightbox="../../media/188cf3ff-58f1-41ea-81aa-76158d8f40c3.png":::

[エクスプローラー] ページの上部にある [クエリの **保存]** ボタンを使用すると、いつでも、注目に値するトラッカー クエリまたは独自のエクスプローラー クエリのいずれかを保存できます。 そこに保存された内容はすべて、[トラッカー] ページの **[保存されたクエリ** ] リストに表示されます。

## <a name="trackers-and-explorer"></a>トラッカーとエクスプローラー

電子メール、コンテンツ、またはOfficeアクティビティ (近日公開予定) を確認する場合でも、エクスプローラーとトラッカーは連携して、セキュリティ リスクと脅威の調査と追跡に役立ちます。 トラッカーは、すべてまとめて、新しい、注目すべき、頻繁に検索される問題を強調表示することで、ユーザーを保護するための情報を提供します。これにより、クラウドに移行するときにビジネスの保護が強化されます。

また、右下隅にある [フィードバック] ボタンをクリックすると、この機能やその他のMicrosoft 365セキュリティ機能に関する **フィードバック** をいつでも提供できます。

:::image type="content" source="../../media/microsoft-365-defender-portal.png" alt-text="Microsoft 365 Defender ポータル" lightbox="../../media/microsoft-365-defender-portal.png":::

## <a name="trackers-and-microsoft-defender-for-office-365"></a>トラッカーとMicrosoft Defender for Office 365

注目に値する脅威を取り上げて、[セーフ添付ファイル](safe-attachments.md)によって検出された高度なマルウェアの脅威を強調しています。 Office 365 Enterprise E5 のお客様で、[Microsoft Defender for Office 365](defender-for-office-365.md)を使用していない場合は、サブスクリプションに含まれている必要があります。 Defender for Office 365は、Office 365 サービスで電子メール フローをフィルター処理する他のセキュリティ ツールがある場合でも、価値を提供します。 ただし、スパム対策と[セーフリンク](safe-links.md)機能は、メインの電子メール セキュリティ ソリューションがOffice 365を使用している場合に最適です。

:::image type="content" source="../../media/policies.png" alt-text="Microsoft 365 Defender ポータルのMicrosoft Defender for Office 365" lightbox="../../media/policies.png":::

今日の脅威に覆われている世界では、従来のマルウェア対策スキャンのみを実行することは、攻撃から十分に保護されないことを意味します。 現在、より高度な攻撃者は、一般的に利用可能なツールを使用して、従来のシグネチャ ベースのマルウェア対策エンジンでは認識されない新しい、難読化された、または遅延された攻撃を作成します。 セーフ添付ファイル機能は、電子メールの添付ファイルを受け取り、仮想環境で起爆して、それらが安全か悪意があるかを判断します。 このデトネーション プロセスは、仮想コンピューター環境で各ファイルを開き、ファイルを開いた後の動作を監視します。 PDF ファイル、圧縮ファイル、Office ドキュメントのいずれであっても、悪意のあるコードはファイル内で非表示にすることができ、対象ユーザーがコンピューターで開いた後にのみアクティブ化できます。 電子メール フロー内のファイルを起爆して分析することで、Defender for Office 365機能は、動作、ファイルの評判、および多くのヒューリスティック ルールに基づいてこれらの脅威を検出します。

新しい注目すべき脅威フィルターでは、添付ファイルセーフ最近検出されたアイテムが強調表示されます。 これらの検出は、電子メール フローまたは他の顧客の電子メールのMicrosoft 365によって以前に検出されなかった新しい悪意のあるファイルであるアイテムを表します。 注目に値する脅威トラッカーの項目に注意を払い、対象ユーザーを確認し、[詳細分析] タブに表示される爆発の詳細を確認します (エクスプローラーでメールの件名をクリックすることで確認できます)。 このタブは、[セーフ添付ファイル] 機能によって検出されたメールにのみ表示されることに注意してください。この注目に値するトラッカーには、そのフィルターが含まれていますが、エクスプローラーで他の検索にこのフィルターを使用することもできます。

## <a name="next-steps"></a>次の手順

- 組織にこれらのOffice 365脅威の調査と対応の機能がまだない場合は、「脅威の調査と対応[の機能Office 365取得する方法](office-365-ti.md)」を参照してください。

- セキュリティ チームに適切なロールとアクセス許可が割り当てられていることを確認します。 グローバル管理者であるか、Microsoft 365 Defender ポータルでセキュリティ管理者または検索および消去ロールが割り当てられている必要があります。 [Microsoft 365 Defender ポータルのアクセス許可に関するページを](permissions-microsoft-365-security-center.md)参照してください。

- Microsoft 365環境に新しいトラッカーが表示されるのを確認します。 利用可能な場合は、Microsoft 365 Defender ポータル<https://security.microsoft.com/threattracker>の **[脅威トラッカー**] ページにトラッカーがあります。

- まだ行っていない場合は、セーフ リンクや[添付ファイルのセーフ](defender-for-office-365.md)など、組織の[Microsoft Defender for Office 365](safe-links.md)の詳細と構成について説明します。[](safe-attachments.md)

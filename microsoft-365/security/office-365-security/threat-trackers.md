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
description: 新しい注目に値するトラッカーを含む脅威トラッカーについて学び、組織がセキュリティ上の懸念事項を引き受けるのに役立ちます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63673247e6e818459207634d68e18c7adb019e41
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154328"
---
# <a name="threat-trackers---new-and-noteworthy"></a>脅威トラッカー - 新機能とNoteworthy 機能 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Office 365調査と](office-365-ti.md)対応機能を使用すると、組織のセキュリティ チームは、サイバーセキュリティの脅威を検出して対策を実行できます。 Office 365脅威の調査と対応の機能には、注目に値するトラッカーを含む脅威追跡機能が含まれます。 これらの新機能と次の手順の概要については、この記事をご覧ください。

> [!IMPORTANT]
> Office 365脅威インテリジェンスは、Microsoft Defender for Office 365プラン 2 と、追加の脅威保護機能です。 詳細については[、「Microsoft Defender for Office 365プラン](https://products.office.com/exchange/advance-threat-protection)と価格」、[および「Microsoft Defender for Office 365サービスの説明」を参照してください](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

## <a name="what-are-threat-trackers"></a>脅威トラッカーとは

脅威トラッカーは、企業に影響を与える可能性のあるさまざまなサイバーセキュリティの問題に関するインテリジェンスを提供する有益なウィジェットとビューです。 たとえば、脅威トラッカーを使用して、マルウェア キャンペーンの傾向に関する情報を表示できます。

![マルウェア キャンペーンを表示する脅威トラッカーの例。](../../media/a883b5ac-8e2b-469a-90e0-f8ad39bb63b7.png)

ほとんどのトラッカー ページには、定期的に更新される傾向の数値、最も大きい問題や最も大きくなった問題を理解するためのウィジェット、エクスプローラーに移動する [アクション] 列のクイック リンクが含まれています。詳細な情報を表示できます。

![エクスプローラーのキャンペーン情報の例。](../../media/e426f220-fdcb-4dd9-99a2-db97dbcf71d5.png)

トラッカーは、計画 2 の Microsoft Defender で取得する多くの素晴[Office 365ほんの一部です](office-365-ti.md)。 脅威トラッカーには[、Noteworth トラッカー](#noteworthy-trackers) [、Trending trackers、Tracked](#trending-trackers)[クエリ](#tracked-queries)、および[保存されたクエリが含まれます](#saved-queries)。

組織で脅威トラッカーを表示して使用するには、Microsoft 365 Defender ポータル ( ) に移動し、[メールと& <https://security.microsoft.com> **の脅威** トラッカー] \> **を選択します**。

> [!NOTE]
> Threat Trackers を使用するには、グローバル管理者、セキュリティ管理者、またはセキュリティ リーダーである必要があります。 「[アクセス許可」を参照Microsoft 365 Defenderします](permissions-microsoft-365-security-center.md)。

### <a name="noteworthy-trackers"></a>注目に値するトラッカー

注目に値するトラッカーは、お客様が知る必要がある大小の脅威とリスクを見つける場所です。 注目に値するトラッカーは、Microsoft 365 環境にこれらの問題が存在するかどうかを確認するのに役立ちます。また、何が起こっているか、および組織の Office 365 の使用にどのような影響を与えるのかについて詳しく説明する記事 (この記事など) へのリンクを参照できます。 大きな新しい脅威 (Wannacry、Petya など) でも、いくつかの新しい課題 (他の重要な注目すべきアイテムである Nemucod など) を生み出す可能性のある既存の脅威に関係ない場合でも、ここで、ユーザーとセキュリティ チームが定期的に検討する必要がある重要な新しいアイテムを見つける必要があります。

通常、注目に値するトラッカーは、新しい脅威を特定し、この機能が提供する追加の可視性が必要になる可能性がある場合に、数週間だけ投稿されます。 脅威の最大のリスクが過ぎたら、その注目すべきアイテムを削除します。 これにより、リストを最新の状態に保ち、他の関連する新しいアイテムと一緒に最新の状態に保つ必要があります。

### <a name="trending-trackers"></a>Trending trackers

傾向トラッカー (以前はキャンペーンと呼ばばれ) は、過去 1 週間に組織のメールで受け取った新しい脅威を強調表示します。

![マルウェア キャンペーン ウィジェットの傾向の例。](../../media/d2ccc1a0-2a1d-4e36-99b5-6766c207772f.png)

トレンド トラッカーを使用すると、より広範な企業環境が攻撃に対して準備されるのを確認するために確認する必要がある新しい脅威のアイデアを提供します。

### <a name="tracked-queries"></a>追跡されたクエリ

追跡されたクエリは、保存されたクエリを利用して、組織のMicrosoft 365を定期的に評価します。 これにより、イベントの傾向が示されます。その他の情報は、次の数か月で提供されます。 追跡されたクエリは自動的に実行され、クエリを再実行する必要なく、最新の情報が提供されます。

![1 つを選択した追跡クエリの例。](../../media/0c556174-06eb-4ae5-b32a-5ff76b9e4f13.png)

### <a name="saved-queries"></a>保存されたクエリ

保存されたクエリは、[トラッカー] セクションにも表示されます。 保存済みクエリを使用すると、検索を毎回作成し戻さずに、より迅速かつ繰り返し取得する一般的なエクスプローラー検索を格納できます。

![1 つを選択して保存されたクエリの例。](../../media/188cf3ff-58f1-41ea-81aa-76158d8f40c3.png)

[エクスプローラー] ページの上部にある [クエリの保存] ボタンを使用して、注目に値するトラッカー クエリまたは独自のエクスプローラー クエリをいつでも保存できます。 そこに保存されたクエリは、[トラッカー] ページ **の [保存済** みクエリ] リストに表示されます。

## <a name="trackers-and-explorer"></a>トラッカーとエクスプローラー

電子メール、コンテンツ、または Office アクティビティ (近日公開予定) を確認する場合でも、エクスプローラーとトラッカーは、セキュリティリスクと脅威の調査と追跡に役立ちます。 トラッカーは、新しい、重要な、頻繁に検索される問題を強調表示することで、ユーザーを保護するための情報を提供します。

また、右下隅にある [フィードバック] ボタンをクリックすると、Microsoft 365または他のセキュリティ機能に関するフィードバックをいつでも提供できます。

![Microsoft 365 Defenderポータル。](../../media/microsoft-365-defender-portal.png)

## <a name="trackers-and-microsoft-defender-for-office-365"></a>トラッカーと Microsoft Defender for Office 365

初の注目に値する脅威では、添付ファイルによって検出された高度なマルウェアの脅威[セーフ強調表示しています](safe-attachments.md)。 E5 のお客様Office 365 Enterprise Microsoft Defender を[Office 365](defender-for-office-365.md)に使用していない場合は、サブスクリプションに含まれている必要があります。 Defender for Office 365は、メール フローをフィルター処理する他のセキュリティ ツールがある場合でも、Office 365します。 ただし、スパム対策とメール セーフ[リンク](safe-links.md)機能は、メインの電子メール セキュリティ ソリューションが電子メール セキュリティ ソリューションを使用している場合にOffice 365。

![Microsoft Defender for Office 365ポータルMicrosoft 365 Defenderします。](../../media/policies.png)

今日の脅威が多い世界では、従来のマルウェア対策スキャンのみを実行すると、攻撃から十分に保護されていないという意味です。 今日のより高度な攻撃者は、一般的に利用可能なツールを使用して、従来の署名ベースのマルウェア対策エンジンでは認識されない新しい、難読化された、または遅延攻撃を作成します。 [セーフ添付ファイル] 機能は、電子メールの添付ファイルを受け取り、仮想環境で電子メールの添付ファイルを削除して、安全か悪意かを判断します。 このデトレーション プロセスは、仮想コンピューター環境内の各ファイルを開き、ファイルを開いた後に何が起こるかを監視します。 PDF、圧縮ファイル、または Office ドキュメントの場合、悪意のあるコードはファイル内で非表示にされ、被害者がコンピューターで開くとアクティブ化されます。 電子メール フロー内のファイルを削除して分析することにより、Defender for Office 365 の機能は、動作、ファイル評価、および多くのヒューリスティック ルールに基づいてこれらの脅威を検出します。

新しい注目すべき脅威フィルターでは、添付ファイルを使用して最近検出されたセーフ強調表示されます。 これらの検出は、新しい悪意のあるファイルであるアイテムを表します。電子メール フローまたは他のMicrosoft 365のメールで、以前は検出されませんでした。 注目に値する脅威トラッカーの項目に注意を払い、対象となったユーザーを確認し、[高度な分析] タブに表示される発起の詳細を確認します (エクスプローラーの電子メールの件名をクリックします)。 このタブは、セーフ 添付ファイル機能によって検出されたメールにのみ表示されます。この注目に値するトラッカーには、そのフィルターが含まれていますが、エクスプローラー内の他の検索に対してそのフィルターを使用することもできます。

## <a name="next-steps"></a>次の手順

- 組織に脅威の調査と応答の機能Office 365していない場合は、「脅威の調査と応答の機能Office 365方法」を[参照してください](office-365-ti.md)。

- セキュリティ チームに正しい役割とアクセス許可が割り当てられているか確認します。 グローバル管理者である必要があります。または、セキュリティ管理者または検索と削除の役割が、管理者ポータルに割りMicrosoft 365 Defenderがあります。 「[アクセス許可」を参照Microsoft 365 Defenderします](permissions-microsoft-365-security-center.md)。

- 新しいトラッカーが環境に表示Microsoft 365します。 利用可能な場合は、ここでトラッカーを見 [つける必要があります](https://https://security.microsoft.com/)。 [メールの **送信] &の** \> **脅威追跡ツールに移動します**。

- まだ行っていない場合は、Microsoft [Defender for Office 365](defender-for-office-365.md)の詳細と構成 (セーフ リンクや添付ファイル[](safe-links.md)など) をセーフ[してください](safe-attachments.md)。

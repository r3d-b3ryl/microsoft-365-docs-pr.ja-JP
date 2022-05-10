---
title: Microsoft Defender for Office 365の脅威エクスプローラーを使用した電子メール セキュリティ
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: マルウェアフィッシングの試行を表示して調査します。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: da555769cbff177fff7de4ee4a25908e1eee3782
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475127"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365の脅威エクスプローラーを使用した電子メール セキュリティ

この記事の内容:

- [電子メールで検出されたマルウェアを表示する](#view-malware-detected-in-email)
- [フィッシング URL を表示し、判定データをクリックする](#view-phishing-url-and-click-verdict-data)
- [自動調査と対応を開始する](#start-automated-investigation-and-response)

> [!NOTE]
> これは、**脅威エクスプローラー (エクスプローラー)**、**電子メール セキュリティ**、**エクスプローラーとリアルタイム検出** (ツール間の違い、操作に必要なアクセス許可など) に関する **3 記事シリーズ** の一部です。 このシリーズの他の 2 つの記事は、[脅威エクスプローラーと脅威エクスプローラーでの脅威の検出](threat-hunting-in-threat-explorer.md)[とリアルタイム検出です](real-time-detections.md)。

この記事では、Microsoft 365セキュリティ機能によって電子メールで検出されたマルウェアやフィッシングの試行を表示し、調査する方法について説明します。

**適用対象:**

- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a>電子メールで検出されたマルウェアを表示する

Microsoft 365テクノロジ別に並べ替えられた電子メールで検出されたマルウェアを表示するには、エクスプローラーの [**[電子メール \> マルウェア**](threat-explorer-views.md#email--malware)] ビュー (またはリアルタイム検出) を使用します。 マルウェアは既定のビューであるため、エクスプローラーを開くとすぐに選択される可能性があります。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**電子メール & コラボレーション**] に移動し、[**エクスプローラー]** または [**リアルタイム検出**] を選択します。 ページに直接移動するには、 <https://security.microsoft.com/threatexplorer> または <https://security.microsoft.com/realtimereports>.

   この例では **、エクスプローラー** を使用します。

   ここから、ビューから開始し、調査する特定の期間 (必要な場合) を選択し、 [エクスプローラーの手順](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)に従ってフィルターにフォーカスを合わせてください。

2. [ **表示** ] ドロップダウン リストで、[ **電子メール** \> **マルウェア** ] が選択されていることを確認します。

3. [ **送信者**] をクリックし、ドロップダウン リストで [ **基本** \> **検出テクノロジ** ] を選択します。

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="マルウェア検出テクノロジ" lightbox="../../media/exploreremailmalwaredetectiontech-newimg.png":::

   検出テクノロジは、レポートのフィルターとして使用できるようになりました。

4. オプションを選択し、[ **更新** ] をクリックしてそのフィルターを適用します (ブラウザー ウィンドウを更新しないでください)。

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="選択された検出テクノロジ" lightbox="../../media/exploreremailmalwaredetectiontech2-new.png":::

   レポートが更新され、選択したテクノロジ オプションを使用して、マルウェアが電子メールで検出した結果が表示されます。 ここから、さらに分析を行うことができます。

### <a name="report-a-message-as-clean-in-explorer"></a>エクスプローラーでメッセージをクリーンとして報告する

エクスプローラーの **[レポート クリーン** ] オプションを使用すると、誤検知としてメッセージを報告できます。 

1. Microsoft 365 Defender ポータルで、[**電子メール & コラボレーション** \> **エクスプローラー**] に移動し、[**表示**] ドロップダウン リストで **[フィッシング]** が選択されていることを確認します。

2. [ **電子メール** ] タブにいることを確認し、報告されたメッセージの一覧から、クリーンとして報告するメッセージを選択します。 

3. [ **アクション] を** クリックして、オプションの一覧を展開します。

4. オプションの一覧を下にスクロールして [ **新しい申請の開始** ] セクションに移動し、[ **レポートクリーン**] を選択します。 ポップアップが表示されます。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/report-clean-option-explorer.png" alt-text="エクスプローラーの [レポート クリーン] オプション" lightbox="../../media/report-clean-option-explorer.png":::

5. スライダーを **[オン]** に切り替えます。 ドロップダウン リストから、メッセージを削除する日数を指定し、必要に応じてメモを追加して、[送信] を選択 **します**。 

## <a name="view-phishing-url-and-click-verdict-data"></a>フィッシング URL を表示し、判定データをクリックする

許可、ブロック、オーバーライドされた URL の一覧など、メール内の URL を介してフィッシングの試行を表示できます。 クリックされた URL を識別するには、[セーフ リンク](safe-links.md)を構成する必要があります。 クリック時の保護と[、セーフ リンク](set-up-safe-links-policies.md)によるクリックの判定のログ記録のために、セーフ リンク ポリシーを設定していることを確認します。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**電子メール & コラボレーション**] に移動し、[**エクスプローラー]** または [**リアルタイム検出**] を選択します。 ページに直接移動するには、 <https://security.microsoft.com/threatexplorer> または <https://security.microsoft.com/realtimereports>.

   この例では **、エクスプローラー** を使用します。

2. [ **表示** ] ボックスの一覧で、[ **メール** \> **フィッシング**] を選択します。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerViewEmailPhishMenu.png" alt-text="フィッシング コンテキストでのエクスプローラーの [表示] メニュー" lightbox="../../media/ExplorerViewEmailPhishMenu.png":::

3. [ **送信者]** をクリックし、ドロップダウン リストで **[URL** \> **] クリックの判定** を選択します。

4. 表示されるオプションで、 **ブロック** や **ブロックのオーバーライド** など、1 つ以上のオプションを選択し、[ **更新** ] をクリックします (ブラウザー ウィンドウを更新しないでください)。

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="URL とクリックの判定" lightbox="../../media/threatexploreremailphishclickverdict-new.png":::

   レポートが更新され、レポートの下の [ **URL** ] タブに 2 つの異なる URL テーブルが表示されます。

   - **上位 URL は** 、フィルター処理したメッセージ内の URL であり、各 URL の電子メール配信アクション数です。 フィッシング メール ビューでは、通常、この一覧には正当な URL が含まれています。 攻撃者は、メッセージに適切な URL と悪い URL を組み合わせて配信しようとしますが、悪意のあるリンクをより興味深く見せようとします。 URL のテーブルは合計メール数で並べ替えられますが、ビューを簡略化するためにこの列は非表示です。

   - **トップ クリック** 数は、クリックされたリンクラップ URL のセーフであり、合計クリック数で並べ替えられます。 ビューを簡略化するために、この列も表示されません。 列ごとの合計数は、クリックされた URL ごとにセーフリンククリックの判定数を示します。 フィッシング メール ビューでは、通常、これらは疑わしい URL または悪意のある URL です。 ただし、ビューには、脅威ではなくフィッシング メッセージ内にある URL が含まれる可能性があります。 ラップされていないリンクの URL クリックはここには表示されません。

   2 つの URL テーブルには、配信アクションと場所によってフィッシングメール メッセージの上位 URL が表示されます。 テーブルには、警告にもかかわらずブロックまたはアクセスされた URL クリックが表示されるため、ユーザーに表示された潜在的な不適切なリンクと、ユーザーがクリックした可能性のあるリンクを確認できます。 ここから、さらに分析を行うことができます。 たとえば、グラフの下には、組織の環境でブロックされた電子メール メッセージの上位 URL が表示されます。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerPhishClickVerdictURLs.png" alt-text="ブロックされたエクスプローラーの URL" lightbox="../../media/ExplorerPhishClickVerdictURLs.png":::

   URL を選択すると、詳細な情報が表示されます。

   > [!NOTE]
   > [URL ポップアップ] ダイアログ ボックスでは、電子メール メッセージのフィルター処理が削除され、環境内の URL の露出の完全なビューが表示されます。 これにより、エクスプローラーで関心のある電子メール メッセージをフィルター処理し、潜在的な脅威である特定の URL を検索し、エクスプローラー ビュー自体に URL フィルターを追加しなくても、環境内の URL 公開に関する理解を広めることができます。

### <a name="interpretation-of-click-verdicts"></a>クリック判定の解釈

電子メールまたは URL ポップアップ、トップ クリック数、およびフィルター処理エクスペリエンスでは、さまざまなクリック判定値が表示されます。

- **なし：** URL の判定をキャプチャできません。 ユーザーが URL をクリックした可能性があります。
- **許可：** ユーザーは URL に移動することができました。
- **ブロック：** ユーザーが URL への移動をブロックされました。
- **保留中の判定:** ユーザーに、起爆保留中のページが表示されました。
- **ブロックされたオーバーライド:** ユーザーが URL への直接移動をブロックされました。 ただし、ユーザーはブロックをオーバーロードして URL に移動します。
- **保留中の判定がバイパスされました。** ユーザーにデトネーション ページが表示されました。 ただし、ユーザーはメッセージをオーバーロードして URL にアクセスします。
- **エラー：** ユーザーにエラー ページが表示されたか、判定のキャプチャ中にエラーが発生しました。
- **失敗：** 判定のキャプチャ中に不明な例外が発生しました。 ユーザーが URL をクリックした可能性があります。

## <a name="start-automated-investigation-and-response"></a>自動調査と対応を開始する

> [!NOTE]
> 自動調査と対応機能は、*Microsoft Defender for Office 365プラン 2* および *Office 365 E5* で利用できます。

[自動調査と対応により、](automated-investigation-response-office.md) セキュリティ運用チームがサイバー攻撃の調査と軽減に費やした時間と労力を節約できます。 セキュリティ プレイブックをトリガーできるアラートの構成に加えて、エクスプローラーのビューから自動調査と応答プロセスを開始できます。 詳細については、「 [例: セキュリティ管理者がエクスプローラーから調査をトリガーする」を](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)参照してください。

## <a name="other-articles"></a>その他の記事

[[電子メール エンティティ] ページを使用して電子メールを調査する](mdo-email-entity-page.md)

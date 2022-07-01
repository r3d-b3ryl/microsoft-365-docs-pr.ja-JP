---
title: Microsoft 365 管理センターの新機能
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
- FRP150
ms.custom:
- MACDashWhatsNew
- AdminSurgePortfolio
- admindeeplinkMAC
description: Microsoft 365 管理センター - 今月追加された機能について説明します。
ms.openlocfilehash: fe801e913e227239b53eb7f1166a3f802f4217ce
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66602582"
---
# <a name="whats-new-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの新機能

::: moniker range="o365-21vianet"

> [!NOTE]
> この記事の情報の一部は、21Vianet によって運用されているOffice 365には適用されない場合があります。

::: moniker-end

[Microsoft 365 管理センター](Microsoft 365 管理センターの概要](admin-overview/admin-center-overview.md)、学習した問題の修正、フィードバックに基づく変更を継続的に追加しています。 一部の機能は、お客様に対して異なる速度でロールアウトされます。 まだ機能が表示されていない場合は、 [対象となるリリースに自分を追加してみてください](manage/release-options-in-office-365.md)。

また、他の Microsoft クラウド サービスの新機能を知りたい場合は、次のようにします。

- [Azure Active Directory の新機能](/azure/active-directory/fundamentals/whats-new)
- [Exchange 管理センターの新機能](/Exchange/whats-new)
- [Microsoft Intune の新機能](/mem/intune/fundamentals/whats-new)
- [Microsoft Purview コンプライアンス ポータルの新機能](/Office365/SecurityCompliance/whats-new)
- [Microsoft 365 Defender の新機能](../security/mtp/whats-new.md)
- [SharePoint 管理センターの新機能](/sharepoint/what-s-new-in-admin-center)
- [Office 更新プログラム](/OfficeUpdates/)
- [Windows リリースの正常性を確認する方法](/windows/deployment/update/check-release-health)

## <a name="may-2022"></a>2022 年 5 月

### <a name="role-based-access-controls-rbac"></a>ロール ベースのアクセス制御 (RBAC)

Microsoft 365 管理センターには、カスタム セキュリティ属性を管理するための 4 つの新しいロールがあります。 これらのロールは、すべてのユーザーが [**ロール**] の下のMicrosoft 365 管理センターで使用できます。

- **属性の割り当て管理者**   サポートされている Azure AD オブジェクトにカスタム セキュリティ属性キーと値を割り当てます。

- **属性の割り当てリーダー**   サポートされている Azure AD オブジェクトのカスタム セキュリティ属性キーと値を読み取ります。

- **属性定義管理者**   カスタム セキュリティ属性の定義を定義および管理します。

- **属性定義リーダー**   カスタム セキュリティ属性の定義を読み取ります。

また、仮想アクセスを管理するために必要なアクセス権のみを管理者に付与できる新しいロールもあります。

- **Virtual Visits 管理者**   管理センターまたは Virtual Visits アプリから、Virtual Visits の情報とメトリックを管理および共有します。

これらのロールの詳細については、 [Azure AD の組み込みロールに](/azure/active-directory/roles/permissions-reference)関するページを参照してください。

### <a name="quick-assist"></a>クイック アシスト

アプリのパフォーマンスとセキュリティを強化するために、クイック アシストを Windows ストアに移動しました。 Windows クイック アシスト アプリを使用すると、ユーザーとエンド ユーザーはリモート接続を介して PC サポートを受け取ったり、提供したりできます。

新しい クイック アシスト ストア アプリでは、パスコードの生成時間が大幅に向上し、アプリケーション エラーが減少します。

詳細については、「[リモート接続で PC の問題を解決する](https://support.microsoft.com/windows/solve-pc-problems-over-a-remote-connection-b077e31a-16f4-2529-1a47-21f6a9040bf3)」と「[クイック アシストのインストール」を](https://support.microsoft.com/windows/install-quick-assist-c17479b7-a49d-4d12-938c-dbfb97c88bca)参照してください。

## <a name="april-2022"></a>2022 年 4 月

### <a name="nps-sentiment-insights"></a>NPS Sentiment Insights

NPS アンケート分析情報は、Microsoft 365 管理センターで利用できる AI 主導のダッシュボードです。

管理センターで、 **正常性** > **製品のフィードバック** > **NPS アンケートの分析情報** に移動します。

この機能は、ユーザーが回答した Microsoft NPS アンケートから派生した実用的な分析情報を取得するような管理者に役立ちます。 詳細については、 [Microsoft 製品 NPS のフィードバックと組織の分析情報を参照してください](manage/manage-feedback-product-insights.md)。

フィードバックに基づいて、各 NPS の詳細なフィードバックのセンチメントを識別する新機能を導入し、Microsoft 365 製品に関してユーザーが感じていることを知ることができます。 **ポジティブ**、**ネガティブ**、**その他** などのセンチメント ラベルは、NPS の逐語フィードバックに割り当てられます。

:::image type="content" source="../media/product-feedback-nps-verbatims.png" alt-text="スクリーンショット: [NPS surveys insights] タブの [製品フィードバック] ダッシュボード":::

NPS アンケート分析情報ダッシュボードのセンチメント機能を使用すると、次のことが可能になります。

- NPS の詳細なフィードバックに基づいて、過去 12 か月間のセンチメント傾向を視覚化します。

- アプリとプラットフォームごとのセンチメントを識別します。

次の 3 つのセンチメントを使用できます。

:::image type="content" source="../media/sentiment-examples.png" alt-text="スクリーンショット: センチメントの例と説明":::

NPS アンケート分析情報ダッシュボードを使用してエクスペリエンスを向上させるために、次の項目を確認することをお勧めします。

- ユーザーにフィードバックを送信するよう促します。

- [製品内アンケート ポリシー](https://config.office.com)が有効になっていることを確認します。

- [Windows エラー報告](/windows/win32/wer/windows-error-reporting)を有効にすることで、診断可能性を向上させます。

> [!NOTE]
> 企業のお客様で、デザイン セッションへの参加に関心がある場合は、次のメールを送信 prosight@microsoft.com

### <a name="microsoft-365-admin-center-search"></a>Microsoft 365 管理センター検索

グローバル検索で検索して **Enter** キーを押すことで、すべての検索結果を別のブラウザー ページに表示できるようになりました。

検索結果の新しい個別のページを使用すると、より包括的な結果の一覧を調べて、ブラウザー ページに簡単に戻って、より効率的な検索エクスペリエンスを実現できます。

:::image type="content" source="../media/whats-new-search-page.png" alt-text="スクリーンショット: 新しいMicrosoft 365 管理センターブラウザー検索ページ":::

### <a name="search-in-distribution-lists-to-add-priority-accounts"></a>配布リストで検索して優先度アカウントを追加する

以前は、ユーザーの名前、電子メール アドレス、役職を使用して優先度アカウントを検索するだけで、優先度の高いアカウントにタグを付けることができました。 この更新プログラムを使用すると、配布リストの優先度アカウントに追加するユーザーを検索できるようになりました。 これにより、効率的な方法でユーザーを一括追加でき、組織内の個々のユーザーにタグを付けるのに必要な時間を短縮できます。

:::image type="content" source="../media/search-by-distribution-list-priority-accounts.png" alt-text="スクリーンショット: 配布リストを使用して追加する優先度アカウントを検索する":::

- 1 つのアクションで、配布リストから最大 50 人のユーザーを優先度アカウントとしてタグ付けできます。

- 部署や役職などのユーザーに関する追加情報は、[優先度アカウント] ページで紹介されています。

- 配布リスト内のユーザー アカウントにのみタグを付けることができます。リスト自体にはタグを付けられません。 既にタグ付けされているユーザーは、配布リスト検索に表示されません。

## <a name="march-2022"></a>2022 年 3 月

### <a name="microsoft-365-lighthouse-ga"></a>Microsoft 365 Lighthouse GA

中小企業は、多くの場合、信頼できる IT パートナーを利用して IT 環境を管理しています。 マネージド サービス プロバイダー (MSP) のマルチテナント管理ポータル[である Microsoft 365 Lighthouse](https://aka.ms/March1SMBPartnerBlog) の一般提供により、パートナーが大規模に顧客をセキュリティで保護しやすくしています。 Microsoft 365 Lighthouseは、パートナーが脅威、異常なサインイン、デバイス コンプライアンス アラートを迅速に特定して対処し、安全を維持できるようにすることで、お客様に完全なエクスペリエンスを提供します。

:::image type="content" source="../media/lighthouse.png" alt-text="スクリーンショット: ダッシュボードをMicrosoft 365 Lighthouseする":::

Microsoft 365 Lighthouseは IT パートナー サービスのみであり、クラウド ソリューション プロバイダー (CSP) プログラムに登録され、Microsoft 365 Business Premium、Microsoft 365 E3、またはライセンスを持つ最大 1,000 人のライセンスユーザーを持つ顧客を管理しているパートナーが利用できます。Microsoft Defender for Business (プレビュー段階) サブスクリプション。 Microsoft CSP に登録されている IT パートナーの場合、Microsoft 365 Lighthouseは組織に無償で提供され、ビジネスの規模と拡大に役立つよう設計されています。 詳細については、[Microsoft 365 Lighthouseヘルプ ライブラリ](../lighthouse/m365-lighthouse-overview.md)を参照してください。

Microsoft 365 Lighthouseの使用を開始するには、「[Microsoft 365 Lighthouseへのサインアップ](../lighthouse/m365-lighthouse-sign-up.md)」を参照してください。 Microsoft 365 Lighthouse、Defender for Business、Microsoft 365 Business Premiumの詳細については、[パートナー ウェビナー シリーズにお問い合わせください](https://aka.ms/M365MDBSeries)。

## <a name="february-2022"></a>2022 年 2 月

### <a name="net-promoter-score-nps-survey-insights"></a>Net の推進スコア (NPS) アンケートの分析情報

これで、Microsoft 365 管理センター内のユーザーからの NPS アンケート データと分析情報を表示できるようになりました。 この新機能を使用すると、エンド ユーザーから NPS アンケートの回答から実用的な分析情報を取得し、問題や懸念事項に対処することで、より高いエンド ユーザーの喜びを実現できます。

管理センターで、 **正常性** > **製品のフィードバック** > **NPS アンケートの分析情報** に移動します。

:::image type="content" source="../media/feedback-whatsnew.png" alt-text="スクリーンショット: Microsoft 365 管理センターの [フィードバック] ページを表示する":::

ユーザーからのフィードバックから、共通のテーマを特定しました。 次に、機械学習モデルの手法を使用してデータ セットをトレーニングし、フィードバックを自動的に上位トピックに整理しました。

利用可能なトピックは 9 つあります。 今後の更新に関するその他のトピックを確認してください。

:::image type="content" source="../media/feedback-nine-topics.png" alt-text="スクリーンショット: 9 つの新しいフィードバック トピックを示しています":::

NPS アンケート分析情報ダッシュボードには、次の 3 つの新しいレポートとピボットも含まれています。

- 過去 12 か月間の NPS 月間 NPS の傾向量
- パッシブ、プロモーター、およびデトラクターを識別できる
- プラットフォームとアプリごとの NPS ボリューム

NPS アンケート分析情報ダッシュボードを使用して、より優れたエクスペリエンスを提供するには、次の手順を実行します。

- エンド ユーザーにフィードバックの送信を促す
- 製品内アンケート ポリシーが有効になっていることを確認する
- Windows エラー報告をオンにして診断を改善する

詳細については、 [Microsoft 製品 NPS のフィードバックと組織の分析情報を参照してください](manage/manage-feedback-product-insights.md)。  

> [!NOTE]
> デザイン セッションに参加したい場合は、次のメールを送信 prosight@microsoft.com

### <a name="microsoft-365-admin-center-video-training"></a>Microsoft 365 管理センタービデオ トレーニング

Microsoft 365 管理センタービデオ トレーニングを更新しました。 [管理 トレーニング ビデオ ライブラリ](https://go.microsoft.com/fwlink/?linkid=2197659) ページに移動して、ビジネス向けに Microsoft 365 を設定および管理する方法について説明します。

:::image type="content" source="../media/admin-library-vid-training.png" alt-text="スクリーンショット: 管理センターのビデオ トレーニング ライブラリを表示する":::

## <a name="july-2021"></a>2021 年 7 月

### <a name="microsoft-365-admin-center-search"></a>Microsoft 365 管理センター検索

これで、<a href="https://go.microsoft.com/fwlink/p/?linkid=2091030" target="_blank">Microsoft 365 管理センター</a>でインシデント ID を検索できるようになりました。 現在のインシデントについては、ソーシャル メディア、業界の出版物、または他の管理者から学ぶことができます。 これで、管理センターに移動して、インシデントの詳細を調べ、組織への影響を理解できるようになりました。 管理センターでインシデント ID を検索するだけです。

:::image type="content" source="../media/incident-id.png" alt-text="スクリーンショット: 管理センターでインシデント ID を検索する":::

### <a name="support-ticket-insight-for-premier-organizations"></a>Premier 組織のチケット分析情報をサポートする

サポートボリュームに関する視覚的な分析情報を得るために、製品別の **ボリュームの傾向** と **ボリュームの傾向** と呼ばれる 2 つのグラフが追加されました。

**[ボリュームの傾向**] タブの定期グラフでは、サポート ケースが月単位で組織の月単位で増加または減少している場合の傾向が強調表示されます。 グラフにポインターを合わせると、毎月作成されたサポート ケースの数を確認できます。

:::image type="content" source="../media/SuppInsight-voltrnd.PNG" alt-text="スクリーンショット: サポート ケースが月単位で組織で増減している場合の傾向を示すグラフ":::

**製品別ボリュームの傾向** グラフには、サポート ケースが最も多い毎月の上位 3 つの製品が表示されます。 テーブルでフィルター処理が有効になっており、 **製品**、 **重大度**、 **日付** で結果をフィルター処理できるようになりました。

:::image type="content" source="../media/SuppInsight-voltrndproduct.PNG" alt-text="スクリーンショット: グラフは、サポート ケースが最も多い毎月の上位 3 製品を示しています":::

また **、チケット** に関するより多くの分析情報を提供するために、**サービス要求の表示** テーブルに重大度と **終了日** という 2 つの新しいフィールドも追加されました。

:::image type="content" source="../media/SuppInsight-date-sev.PNG" alt-text="スクリーンショット: 重大度と日付によるサポート チケットの並べ替えを示す表。":::

<a href="https://go.microsoft.com/fwlink/p/?linkid=2166757" target="_blank">Microsoft 365 管理センター</a>でこれらの更新プログラムを確認するには、左側のナビゲーション ウィンドウの **[サポート** > **ビュー サービス要求**] に移動します。

## <a name="june-2021"></a>2021 年 6 月

### <a name="microsoft-365-admin-center-search"></a>Microsoft 365 管理センター検索

いくつかの新しいカテゴリが検索機能に追加されました。

- これで、グローバル検索で Microsoft 365 管理者ロールを検索し、任意のページからロールの割り当てを迅速に表示および管理できるようになりました。 たとえば、**Intune管理者を検索します**。

- これで、グローバル検索を通じて簡単なセットアップ エクスペリエンスを見つけることができます。 これにより、お客様とチームが新機能の使用方法をすばやく開始できます。 たとえば、有効期限 **が切れないパスワードを検索します**。

管理センターでの検索の詳細については、[Microsoft 365 管理センターの検索に関するページを](manage/search-in-the-mac.md)参照してください。

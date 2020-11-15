---
title: エンドポイント データ損失防止の使用
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Microsoft 365 エンドポイント データ損失防止 (EPDLP) の場所を使用するようにデータ損失防止 (DLP) ポリシーを構成する方法を説明します。
ms.openlocfilehash: 64cdfeab4b527dd3b84e7586d1419e5bf8b383df
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073106"
---
# <a name="using-endpoint-data-loss-prevention"></a>エンドポイント データ損失防止の使用

この記事では、デバイスを場所として使用する DLP ポリシーを作成および変更する 3 つのシナリオについて説明します。

## <a name="dlp-settings"></a>DLP の設定

作業を開始する前に、デバイスのすべての DLP ポリシーに適用する DLP 設定を済ませる必要があります。以下のことを実施するポリシーを作成する場合は、これらを構成する必要があります。

- クラウド出口制限
- 許可しないアプリの制限

または

- 監視対象外のファイル パスを除外する場合

  > [!div class="mx-imgBorder"]
  > ![DLP の設定](../media/endpoint-dlp-1-using-dlp-settings.png)

### <a name="file-path-exclusions"></a>ファイルパスの除外

DLP が多すぎるか、関心のあるファイルが含まれていない可能性があるため、DLP の監視、DLP アラート、および DLP ポリシーの適用から特定のパスを除外したい場合があります。除外した場所のファイルは監査されず、その場所で作成または変更されたファイルは、DLP ポリシーの強制の対象になりません。DLP 設定では、パスを除外するように構成できます。

このロジックを使用して、除外パスを構築できます。

- 有効なファイルパスが ' \ ' で終わっている場合は、フォルダーの直下にあるファイルだけになります。 <br/>例: C:\Temp\

- 有効なファイルパスが ‘\*’で終わっている場合は、そのフォルダーの直下のファイルという以外に、サブフォルダーの直下にあるファイルということになります。 <br/>例: C:\Temp\*

- 有効なファイルパスが ‘\’ または ‘\*’以外で終わっている場合は、フォルダーとすべてのサブフォルダーの直下にあるすべてのファイルになります。 <br/>例: C:\Temp

- 両側の ' \ ' の間にあるワイルドカードを使用したパス。 <br/>例: C:\Users\*¥ Desktop\

- 両側の ' \ ' の間にあるワイルドカードと' (数値) ' のあるパスは、サブフォルダーの正確な数を指定します。 <br/>例: C:\Users\*(1) \Downloads\

- システム環境変数を含むパス。 <br/>例: %SystemDrive%\Test\*

- 上記のすべての組み合わせ。 <br/>例: %SystemDrive%\Users\*\Documents\*(2) ¥ Sub\

### <a name="service-domains"></a>サービスドメイン

エンドポイント DLP ポリシー クラウド アップロード アクセス制限を適用する場合、このリストに Microsoft Edge Chromium が指定するドメインを追加できます。 

リスト モードが **ブロック** に設定されている場合、ユーザーは、そのドメインに機密アイテムをアップロードできません。アイテムが DLP ポリシーと一致するためにアップロード アクションがブロックされた場合、DLP は警告を生成するか、機密アイテムのアップロードをブロックします。

リスト モードが **許可** に設定されている場合、ユーザーはこれらのドメイン * *_限定_* _ で機密アイテムをアップロードでき、その他すべてのドメインへのアップロードは制限されます。

### <a name="unallowed-apps"></a>許可されていないアプリ

ポリシーで _ *許可されていないアプリとブラウザーによるアクセス* * の設定がオンで、ユーザーがこのアプリを使用して保護ファイルにアクセスする場合、以下のいずれかになります。アクティビティは許可される、ブロックされる、または、ブロックされるがユーザーがこの制限を上書きできる。すべてのアクティビティが監査され、アクティビティ エクスプローラーで確認できます。

### <a name="unallowed-browsers"></a>許可されていないブラウザー

実行可能ファイル名で識別されるブラウザーを追加します。これらのブラウザーでは、クラウド サービスへのアップロードの制限がブロックまたは上書きのブロックに設定されている強制された DLP ポリシーの条件に一致するファイルへのアクセスがブロックされます。これらのブラウザーがファイルへのアクセスからブロックされている場合、エンドユーザーには、Edge Chromium 経由でファイルを開くように依頼するトースト通知が表示されます。

[!IMPORTANT]
実行可能ファイルへのパスは含めず、実行可能ファイル名 (例: browser.exe) のみを含めてください。

## <a name="tying-dlp-settings-together"></a>DLP 設定の結合

エンドポイント DLP と Edge Chromium Web ブラウザーを使用すると、許可されていないクラウド アプリとサービスに対して、機密アイテムの意図しない共有を制限できます。Edge Chromium は、アイテムがエンドポイント DLP ポリシーによって制限されていることを理解し、アクセス制限を適用します。

適切に構成されている DLP ポリシーと Edge Chromium ブラウザーの場所としてエンドポイント DLP を使用する場合、これらの設定で定義されている許可されていないブラウザーは、DLP ポリシー コントロールに一致する機密アイテムにアクセスできません。その代わりに、ユーザーは Edge Chromium を使用するようにリダイレクトされます。 Edge Chromiumは、DLP ポリシーによって課せられる制限を理解しているため、DLP ポリシーの条件が満たされた場合にアクティビティをブロックまたは制限することができます。

この制限を使用するには、次の3つの重要な要素を構成する必要があります。

1. 機密アイテムの共有を禁止する場所 (サービス、ドメイン、IP アドレス) を指定します。

2. DLP ポリシーが一致した場合に、特定の機密アイテムへのアクセスを許可しないブラウザーを追加します。

3. **クラウドサービスへアップロード** と **許可していないブラウザーからのアクセス** の設定をオンにし、DLP ポリシーを構成してから、これらの場所でアップロードを制限する機密アイテムの種類を定義します。

新しいサービス、アプリ、およびポリシーを継続的に追加して、制限を拡張、強化しながら、ビジネスへのニーズを満たし機密データを保護できます。 

この構成により、データが安全に維持でき、ユーザーが機密情報以外のアイテムにアクセスしたり、共有したりすることを禁止または制限する不必要な制約も回避できます。

## <a name="endpoint-dlp-policy-scenarios"></a>エンドポイント DLP ポリシーのシナリオ

エンドポイント DLP 機能と、それらが DLP ポリシーでどのように示されるのかを理解しやすくするために、いくつかのシナリオをまとめて説明します。エンドポイント DLP が一般提供されると、すべてのエンドポイント DLP コンテンツがメインの DLP コンテンツ セットに組み込まれます。

> [!IMPORTANT]
> これらのエンドポイント DLP のシナリオは、DLP ポリシーの作成と調整に関する公式な手順ではありません。一般的な状況で DLP ポリシーを使用する必要がある場合は、次のトピックを参照してください。
>- [データ損失防止の概要](data-loss-prevention-policies.md)
>- [DLP の既定ポリシーの概要](get-started-with-the-default-dlp-policy.md)
>- [テンプレートから DLP ポリシーを作成する](create-a-dlp-policy-from-a-template.md)
>- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>シナリオ 1: テンプレートからポリシーを作成する (監査のみ)

これらのシナリオでは、デバイスがすでにオンボードされており、アクティビティ エクスプローラーにレポートされている必要があります。デバイスがオンボードされていない場合は、 「[エンドポイント データ損失防止を開始する](endpoint-dlp-getting-started.md)」を参照してください。

1. [データ損失防止ポリシー ページ](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開きます。

2. **[ポリシーの作成]** を選びます。

3. このシナリオでは、 **[プライバシー]** を選択して、" **米国の個人情報 (PII) データ** " を選んでから、 **[次へ]** を選びます。

4. **[デバイス]** を除くすべての場所で **[状態]** フィールドをオフにします。 **[次へ]** を選択します。

5. 既定の **[確認してテンプレートの設定をカスタマイズする]** の選択を承認して、 **[次へ]** を選択します。

6. 既定の **[保護アクション]** の値を承認して、 **[次へ]** を選択します。

7. **[Windows デバイスでアクティビティを監査または制限する]** を選択して、 **[監査のみ]** に設定されたアクションはそのままにしておきます。 **[次へ]** を選択します。

8. 既定の **[先にテストを行います]** を承認し、 **[テスト モードでポリシーのヒントを表示]** を選択します。 **[次へ]** を選択します。

9. 設定を確認し、 **[送信]** を選択します。

10. 新しい DLP ポリシーがポリシー一覧に表示されます。

11. 監視対象エンドポイントのデータについてアクティビティ エクスプローラーを確認します。デバイスの [場所] フィルターを設定してポリシーを追加してから、ポリシー名でフィルター処理して、このポリシーの影響を確認します。必要な場合は、「[アクティビティ エクスプローラーを使用して作業を開始する](data-classification-activity-explorer.md)」を参照してください。

12. 米国の個人情報 (PII) データの条件をトリガーするコンテンツを含むテストを組織外のユーザーと共有してみます。この試行により、ポリシーがトリガーされます。

13. このイベントについてアクティビティ エクスプローラーを確認します。

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a>シナリオ 2: 既存のポリシーを変更し、通知を設定

1. [データ損失防止ポリシー](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開く。

2. シナリオ １ で作成した **米国の個人情報 (PII) データ** ポリシーを選択します。

3. **[ポリシーの編集]** を選びます。

4. **詳細な DLP ルール** ページに移動し、 **米国の個人を特定できる情報が検出された低ボリュームのコンテンツ** を編集します。

5. **[インシデント レポート]** セクションまで下にスクロールして、 **[ルールの一致が発生したときに管理者に通知を送信します]** を **[オン]** にします。メールの通知は、管理者と、受信者のリストに追加する他のユーザーに自動的に送信されます。 

   > [!div class="mx-imgBorder"]
   > ![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)
   
6. このシナリオの目的で、 **アクティビティーがこのルールに一致する度に通知を送信** を選択します。

7. **[保存]** を選択します。

8. **[次へ]** を選択し、ポリシーの変更を **[送信]** して、以前の設定をすべて保持します。

9. 米国の個人情報 (PII) データの条件をトリガーするコンテンツを含むテストを組織外のユーザーと共有してみます。この試行により、ポリシーがトリガーされます。

10. このイベントについてアクティビティ エクスプローラーを確認します。

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a>シナリオ 3: 既存のポリシーを変更し、上書きを許可する操作をブロック

1. [データ損失防止ポリシー](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開く。

2. シナリオ １ で作成した **米国の個人情報 (PII) データ** ポリシーを選択します。

3. **[ポリシーの編集]** を選びます。

4. **詳細な DLP ルール** ページに移動し、 **米国の個人を特定できる情報が検出された低ボリュームのコンテンツ** を編集します。

5. **Windows デバイスでアクティビティを監査または制限** セクションまでスクロールして、アクティビティごと対応するアクションに **上書きをブロック** を設定します。

   > [!div class="mx-imgBorder"]
   > ![上書きアクションのブロックを設定](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)
   
6. **[保存]** を選択します。

7. **米国の個人情報が検出された大量のコンテンツ** の手順4から手順７を繰り返します。

8. **[次へ]** を選択し、ポリシーの変更を **[送信]** して、以前の設定をすべて保持します。

9. 米国の個人情報 (PII) データの条件をトリガーするコンテンツを含むテストを組織外のユーザーと共有してみます。この試行により、ポリシーがトリガーされます。

   クライアント デバイスに次のようなポップアップが表示されます。

   > [!div class="mx-imgBorder"]
   > ![エンドポイント DLP クライアントが上書き通知をブロックしました](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. イベントのアクティビティエクスプローラーを確認します。

## <a name="see-also"></a>関連項目

- [エンドポイント データ損失防止について](endpoint-dlp-learn-about.md)
- [エンドポイント データ損失防止を開始する](endpoint-dlp-getting-started.md)
- [データ損失防止の概要](data-loss-prevention-policies.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)
- [Windows 10 マシン用のオンボーディングツールとメソッド](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure Active Directory (AAD) が参加しました](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [DLP の既定ポリシーの概要](get-started-with-the-default-dlp-policy.md)
- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)

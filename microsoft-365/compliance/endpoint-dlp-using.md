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
ms.openlocfilehash: 02cc958f816c2335a24923cf7fc16b80b9806d9c7811457e88080be50438ce48
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53814183"
---
# <a name="using-endpoint-data-loss-prevention"></a>エンドポイント データ損失防止の使用

この記事では、デバイスを場所として使用する DLP ポリシーを作成および変更する 3 つのシナリオについて説明します。

## <a name="dlp-settings"></a>DLP の設定

作業を開始する前に、デバイスのすべての DLP ポリシーに適用する DLP 設定を済ませる必要があります。 実施するポリシーを作成する場合は、次のようにこれらを設定する必要があります。

- クラウド出口制限
- 許可しないアプリの制限

または

- 監視対象外のファイル パスを除外する場合

  > [!div class="mx-imgBorder"]
  > ![DLP の設定](../media/endpoint-dlp-1-using-dlp-settings.png)

### <a name="file-path-exclusions"></a>ファイルパスの除外

DLP うるさすぎ、関心のあるファイルが含まれないので、デバイス上のDLP 監視、DLP 警告、および DLP ポリシー適用から特定のパスを除外したくなることがあります。 これらの場所にあるファイルは監査されず、その場所で作成または変更されたファイルは、DLP ポリシー適応の対象になりません。 DLP 設定では、パスを除外するように構成できます。

このロジックを使用して、除外パスを構築できます。

- 有効なファイルパスが ' \ ' で終わっている場合は、フォルダーの直下にあるファイルだけになります。 <br/>例: C:\Temp\

- 有効なファイルパスが ‘\*’で終わっている場合は、そのフォルダーの直下のファイルという以外に、サブフォルダーの直下にあるファイルということになります。 <br/>例: C:\Temp\*

- 有効なファイルパスが ‘\’ または ‘\*’以外で終わっている場合は、フォルダーとすべてのサブフォルダーの直下にあるすべてのファイルになります。 <br/>例: C:\Temp

- 両側の ' \ ' の間にあるワイルドカードを使用したパス。 <br/>例: C:\Users\*¥ Desktop\

- 両側の ' \ ' の間にあるワイルドカードと' (数値) ' のあるパスは、サブフォルダーの正確な数を指定します。 <br/>例: C:\Users\*(1) \Downloads\

- システム環境変数を含むパス。 <br/>例: %SystemDrive%\Test\*

- 上記のすべての組み合わせ。 <br/>例: %SystemDrive%\Users\*\Documents\*(2) ¥ Sub\

### <a name="unallowed-apps"></a>許可されていないアプリ

ポリシーで **許可されていないアプリとブラウザーによるアクセス** の設定がオンで、ユーザーがこのアプリを使用して保護ファイルにアクセスする場合、アクティビティが許可されるかブロックされますが、ユーザーはこの制限を上書きできます。 すべてのアクティビティが監査され、アクティビティエクスプローラーで確認できます。

> [!IMPORTANT]
> 実行可能ファイルへのパスは含めず、実行可能ファイル名 (browser.exe など) のみを含めてください。

### <a name="unallowed-bluetooth-apps"></a>許可されていない Bluetooth アプリ

ポリシーによって保護されているファイルを特定の Bluetooth アプリ経由でユーザーが転送できないようにします。

### <a name="browser-and-domain-restrictions"></a>ブラウザーとドメインの制限
ポリシーに一致する機密ファイルが、無制限のクラウド サービス ドメインと共有されるのを制限します。

#### <a name="service-domains"></a>サービスドメイン

ポリシーによって保護されている機密ファイルを Microsoft Edge の特定のサービス ドメインにアップロードできるかどうかを制御できます。

リストモードが **ブロック** に設定されている場合、ユーザーは、これらのドメインに機密アイテムをアップロードできません。 アイテムが DLP ポリシーと一致するためにアップロードアクションがブロックされた場合、DLP が警告を生成するか、機密アイテムのアップロードをブロックします。

リスト モードが **許可** に設定されている場合、ユーザーはこれらのドメイン **_限定_** で機密アイテムをアップロードでき、その他すべてのドメインへのアップロードは制限されます。

> [!IMPORTANT]
> サービス制限モードが "許可" に設定されている場合、制限を適用する前に、少なくとも 1 つのサービス ドメインを構成する必要があります。

#### <a name="unallowed-browsers"></a>許可されていないブラウザー

実行可能ファイル名で識別された、クラウド サービスへのアップロードの制限がブロックまたは上書きのブロックに設定されている強制された DLP ポリシーの条件に一致するファイルへのアクセスがブロックされるブラウザーを追加します。 これらのブラウザーがファイルへのアクセスからブロックされている場合、エンドユーザーには、Edge Chromium 経由でファイルを開くように依頼するトースト通知が表示されます。

### <a name="business-justification-in-policy-tips"></a>ポリシー ヒントでの業務上の正当な理由

DLP ポリシー ヒントの通知で、ユーザーによる業務上の正当な理由オプションの操作を制御します。 このオプションは、DLP ポリシーの **[オーバーライド付きブロック]** 設定で保護されているアクティビティをユーザーが実行したときに表示されます。 以下のいずれかのオプションを選択できます。

- 既定では、ユーザーは組み込みの業務上の正当な理由を選択するか、独自のテキストを入力できます。
- ユーザーは、組み込みの業務上の正当な理由のみを選択できます。
- ユーザーは、自分自身の正当な理由のみを入力できます。

### <a name="always-audit-file-activity-for-devices"></a>デバイスのファイル アクティビティを常に監査する

既定では、デバイスがオンボードされると、Office、PDF、CSV ファイルのアクティビティが自動的に監査され、アクティビティ エクスプローラーで確認できるようになります。 オンボーディングされたデバイスがアクティブなポリシーに含まれている場合にのみ、このアクティビティを監査する場合は、この機能をオフにします。

ファイル アクティビティは、アクティブ ポリシーに含まれているかどうかに関係なく、常にオンボードされたデバイスで監査されます。

## <a name="tying-dlp-settings-together"></a>DLP 設定の結合

エンドポイント DLP および Microsoft Edge Chromium Web ブラウザーを使用すると、許可されていないクラウドアプリとサービスで意図しない機密アイテムの共有を制限できます。 Microsoft Edge Chromium では、アイテムがエンドポイント DLP ポリシーによって制限される場合を把握して、、アクセス制限を適用しています。

正常に構成されている DLP ポリシーと Microsoft Edge Chromium ブラウザーがある場所としてエンドポイント DLP を使用する場合、これらの設定で定義されている許可されていないブラウザーは、DLP ポリシーコントロールに一致する機密アイテムへアクセスできません。 その代わりに、ユーザーは Microsoft Edge Chromium および Microsoft Edge Chromium を使用するようにリダイレクトされます。 DLP ポリシーが適応される制限を把握することで、DLP ポリシーの条件が満たされた場合にアクティビティをブロックまたは制限することができます。

この制限を使用するには、次の3つの重要な要素を構成する必要があります。

1. 機密アイテムの共有を禁止する場所 (サービス、ドメイン、IP アドレス) を指定します。

2. DLP ポリシーが一致した場合に、特定の機密アイテムへのアクセスを許可しないブラウザーを追加します。

3. **クラウドサービスへアップロード** と **許可していないブラウザーからのアクセス** の設定をオンにし、DLP ポリシーを構成してから、これらの場所でアップロードを制限する機密アイテムの種類を定義します。

新しいサービス、アプリ、およびポリシーを継続的に追加して、制限を拡張、強化しながら、ビジネスへのニーズを満たし機密データを保護できます。 

この構成により、データが安全に維持でき、ユーザーが機密情報以外のアイテムにアクセスしたり、共有したりすることを禁止または制限する不必要な制約も回避できます。

## <a name="endpoint-dlp-policy-scenarios"></a>エンドポイント DLP ポリシーシナリオ

エンドポイント DLP 機能、および DLP ポリシーで表示される方法を把握するために、いくつかのシナリオをまとめてましたので、確認してください。

> [!IMPORTANT]
> これらのエンドポイント DLP シナリオは、DLP ポリシーの作成と調整に関する公式な手順ではありません。 一般的な状況で DLP ポリシーを使用する必要がある場合は、次のトピックを参照してください。

>- [データ損失防止について](dlp-learn-about-dlp.md)
>- [DLP の既定ポリシーの概要](get-started-with-the-default-dlp-policy.md)
>- [テンプレートから DLP ポリシーを作成する](create-a-dlp-policy-from-a-template.md)
>- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>シナリオ 1: テンプレートからポリシーを作成 (監査のみ)

これらのシナリオでは、デバイスが既にオンで、アクティビティエクスプローラーに報告されている必要があります。 まだデバイスをオンにしていない場合は、[エンドポイントのデータ損失防止 (プレビュー) を開始](endpoint-dlp-getting-started.md)を参照してください。

1. [データ損失防止ポリシー ページ](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開きます。

2. **[ポリシーの作成]** を選びます。

3. このシナリオでは、**[プライバシー]** を選択して、"**米国の個人情報 (PII) データ**" を選んでから、**[次へ]** を選びます。

4. **状態** フィールドを **デバイス** を除くすべての場所でオフにします。 **[次へ]** を選択します。

5. 規定の **確認してテンプレートから設定をカスタマイズ** の選択を承認して、**次へ** を選択します。

6. 既定の **保護アクション** の値を承認して、**次へ** を選択します。

7. **Windows デバイスのアクティビティを監査または制限** を選択して、**監査のみ** に設定されたアクションはそのままにしておきます。 **[次へ]** を選択します。

8. 規定の **初めにテストします** を承認し、**テストモードでポリシーのヒントを表示** を選択します。 **[次へ]** を選択します。

9. 設定を確認し、**送信** を選択します。

10. 新しい DLP ポリシーがポリシー一覧に表示されます。

11. 監視対象エンドポイントのデータのアクティビティエクスプローラーを確認します。 デバイスがある場所のフィルターを設定し、ポリシーを追加してから、ポリシー名でフィルター処理を行って、このポリシーの影響を確認します。 必要に応じて、[アクティビティ エクスプローラーの使用を開始](data-classification-activity-explorer.md)を参照してください。

12. 組織外のユーザーと米国の個人情報 (PII) データの条件をトリガーするコンテンツを含むテストを共有。 これによって、ポリシーがトリガーされます。

13. イベントのアクティビティエクスプローラーを確認します。

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a>シナリオ 2: 既存のポリシーを変更し、通知を設定

1. [データ損失防止ポリシー](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開く。

2. シナリオ １ で作成した **米国の個人情報 (PII) データ** ポリシーを選択します。

3. **[ポリシーの編集]** を選びます。

4. **詳細な DLP ルール** ページに移動し、**米国の個人を特定できる情報が検出された低ボリュームのコンテンツ** を編集します。

5. **インシデントリポート** セクションまでスクロールして、**ルールが一致する場合、管理者に通知を送信** を **オン** に設定します。 メールの通知は、管理者と、受信者のリストに追加する他のユーザーに自動的に送信されます。 

   > [!div class="mx-imgBorder"]
   > ![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)
   
6. このシナリオの目的で、**アクティビティーがこのルールに一致する度に通知を送信** を選択します。

7. **[保存]** を選択します。

8. **次へ** を選択して、ポリシーの変更を **送信** を選択することで、すべての前の設定を保持します。

9. 組織外のユーザーと米国の個人情報 (PII) データの条件をトリガーするコンテンツを含むテストを共有。 これによって、ポリシーがトリガーされます。

10. イベントのアクティビティエクスプローラーを確認します。

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a>シナリオ 3: 既存のポリシーを変更し、上書きを許可する操作をブロック

1. [データ損失防止ポリシー](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開く。

2. シナリオ １ で作成した **米国の個人情報 (PII) データ** ポリシーを選択します。

3. **[ポリシーの編集]** を選びます。

4. **詳細な DLP ルール** ページに移動し、**米国の個人を特定できる情報が検出された低ボリュームのコンテンツ** を編集します。

5. **Windows デバイスでアクティビティを監査または制限** セクションまでスクロールして、アクティビティごと対応するアクションに **上書きをブロック** を設定します。

   > [!div class="mx-imgBorder"]
   > ![上書きアクションのブロックを設定](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)
   
6. **[保存]** を選択します。

7. **米国の個人情報が検出された大量のコンテンツ** の手順4から手順７を繰り返します。

8. **次へ** を選択して、ポリシーの変更を **送信** を選択することで、すべての前の設定を保持します。

9. 組織外のユーザーと米国の個人情報 (PII) データの条件をトリガーするコンテンツを含むテストを共有。 これによって、ポリシーがトリガーされます。

   クライアントデバイスに次のようなポップアップが表示されます。

   > [!div class="mx-imgBorder"]
   > ![エンドポイント DLP クライアントが上書き通知をブロックしました](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. イベントのアクティビティエクスプローラーを確認します。

## <a name="see-also"></a>関連項目

- [エンドポイント データ損失防止について](endpoint-dlp-learn-about.md)
- [エンドポイント データ損失防止を開始する](endpoint-dlp-getting-started.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [Windows 10 マシン用のオンボーディングツールとメソッド](/microsoft-365/compliance/dlp-configure-endpoints)
- [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure Active Directory (AAD) が参加しました](/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [DLP の既定ポリシーの概要](get-started-with-the-default-dlp-policy.md)
- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)

---
title: IT 管理者向けドキュメントOfficeコンテンツを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: tutorial
ms.localizationpriority: medium
ms.prod: m365-security
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ROBOTS: NOINDEX,NOFOLOW
description: 管理者は、ドキュメント内のアクティブ なコンテンツをブロックするポリシーを作成するOfficeできます。
ms.openlocfilehash: 33d53ab14fec1b6cd16b8de95befe8bc8a898e16
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468923"
---
# <a name="manage-active-content-in-office-documents"></a>Office ドキュメントでアクティブなコンテンツを管理する

> [!NOTE]
> この記事で説明する機能はプレビューで、すべてのユーザーが利用できる機能ではなく、変更される可能性があります。

Officeがアクティブ なコンテンツを含む場合、ドキュメントを自動的に更新、更新、または _実行できます_。 アクティブ なコンテンツの例としては、マクロ、ActiveXコントロール、Officeがあります。アクティブ コンテンツは、ユーザーに強力で便利な機能を提供できますが、攻撃者はアクティブ コンテンツを使用してマルウェアを配信する可能性があります。

管理者は、アクティブ なコンテンツの使用を特定のユーザー セットに制限する組織ポリシー (グループ ポリシーまたはクラウド ポリシー) を作成したり、アクティブ なコンテンツを完全に無効にしたりできます。 ユーザーは、ファイル オプションの信頼センターで、Officeセキュリティ センターでOfficeの\>セキュリティとプライバシーの設定 **を** \> **構成できます**。

以前は、ユーザーがドキュメントを信頼できるドキュメントとして識別した場合、管理者が Office ドキュメント内のアクティブ なコンテンツをブロックするようにポリシーを構成した場合でも、ユーザーの選択によってアクティブ コンテンツの実行が許可されました。 管理者が設定したポリシーは、信頼できるドキュメントのユーザー ID よりも優先されます。 この動作の変更により、ユーザーに問題が発生する可能性があります。

更新されたセキュリティ センター ロジックについては、次の図で説明します。

:::image type="content" source="../media/office-trust-center-flow.png" alt-text="ポータルの信頼センター ロジックを説明するMicrosoft 365 Defenderグラフ" lightbox="../media/office-trust-center-flow.png":::

1. ユーザーがアクティブなコンテンツをOfficeドキュメントを開きます。

2. ドキュメントが信頼できる場所にある場合は、アクティブなコンテンツを有効にした状態でドキュメントが開きます。 ドキュメントが信頼できる場所からではない場合、評価は続行されます。

3. 更新された動作が有効になります。
   - 以前は、次に評価された設定は、ユーザーが信頼できるドキュメントとしてこのドキュメントを識別していた場合でした。 有効にした場合は、アクティブなコンテンツが有効な状態でドキュメントが開きます。
   - ここで、ユーザーがドキュメントを信頼できるドキュメントとして識別したかどうかは、ここでは考慮されません (手順 8 で現在)。

     動作の基本的な変更については、クラウド ポリシー (手順 4)、グループ ポリシー (手順 6)、ローカル設定 (手順 7) を確認してから、信頼できるドキュメントのユーザー指定を検討します。 これらの手順の 1 つがアクティブ コンテンツへのアクセスをブロックし、どの手順もユーザーの上書きを許可しない場合、信頼できるドキュメントとしてのドキュメントのユーザー ID は関係ありません。

4. クラウド ポリシーは、この種類のアクティブ コンテンツが許可またはブロックされる場合にチェックされます。 アクティブなコンテンツがブロックされていない場合、評価は手順 6 に進みます。

   アクティブ なコンテンツがポリシーによってブロックされている場合は、手順 5 でエクスペリエンスについて説明します。

5. ドキュメントの開きは、信頼バーの通知でブロックされます。 次に何が起こるかは、ポリシーのユーザーオーバーライド設定によって制御されます。a. **ユーザーの上書きは許可されません**: ユーザーはドキュメントを開く事ができません。評価は停止します。
   b. **ユーザーの上書きが許可** されている: ユーザーは信頼バーのリンクをクリックして、アクティブなコンテンツを有効にしたドキュメントを開きます。

6. グループ ポリシーがチェックされ、この種類のアクティブ コンテンツが許可またはブロックされるのか確認されます。 アクティブ なコンテンツがブロックされていない場合、評価は手順 7 に進みます。

   アクティブ なコンテンツがポリシーによってブロックされている場合は、手順 5 でエクスペリエンスについて説明します。

7. ローカル設定がチェックされ、この種類のアクティブ なコンテンツが許可またはブロックされるのか確認されます。 アクティブなコンテンツがブロックされている場合、ドキュメントの開きは、信頼バーの通知でブロックされます。 アクティブなコンテンツがブロックされていない場合、評価は続行されます。

8. ユーザーが以前にドキュメントを信頼できるドキュメントとして識別した場合、アクティブなコンテンツを有効にした状態でドキュメントが開きます。 開かされていない場合は、ドキュメントの開きがブロックされます。

## <a name="what-is-a-trusted-document"></a>信頼できるドキュメントとは

信頼できるドキュメントはOfficeマクロ、ActiveX コントロール、およびドキュメント内の他の種類のアクティブ なコンテンツに対するセキュリティ プロンプトなしで開くドキュメントです。 保護されたビューまたは Application Guard は、ドキュメントを開くのに使用されません。 ユーザーが信頼できるドキュメントを開き、すべてのアクティブ なコンテンツが有効になっている場合。 ドキュメントに新しいアクティブ コンテンツが含まれている場合や、既存のアクティブ コンテンツに対する更新プログラムが含まれている場合でも、ユーザーは次回ドキュメントを開く時にセキュリティ プロンプトを受け取れません。

この動作のため、ユーザーはドキュメント ソースを信頼している場合にのみ、ドキュメントを明確に信頼する必要があります。

管理者がポリシーを使用してアクティブ コンテンツをブロックする場合、またはユーザーがアクティブ コンテンツをブロックする信頼センター設定を設定した場合、アクティブ コンテンツはブロックされたままです。

詳細については、次の資料を参照してください。

- [信頼できるドキュメント](https://support.microsoft.com/topic/trusted-documents-cf872bd8-47ec-4c02-baa5-1fdba1a11b53)
- [信頼できる場所を追加、削除、または変更する](https://support.microsoft.com/topic/add-remove-or-change-a-trusted-location-7ee1cdc2-483e-4cbb-bcb3-4e7c67147fb4)
- [ファイル内のアクティブ なコンテンツ タイプ](https://support.microsoft.com/topic/active-content-types-in-your-files-b7ff2e8a-4055-47d4-8c7d-541e19f62bea)

## <a name="configure-trusted-document-settings-in-office-policies"></a>セキュリティ ポリシーで信頼できるドキュメントOffice構成する

管理者は、組織内のユーザーを構成Office多くの方法があります。 次に例を示します。

- **Office クラウド** ポリシー サービス: Office アプリのファイルにアクセスするデバイス上のユーザーに適用されるユーザー ベースのポリシーを、Azure AD アカウントで設定します。 クラウド ポリシー サービスでクラウド [ポリシー Office構成を作成する](/DeployOffice/overview-office-cloud-policy-service)手順Office[参照してください](https://config.office.com/officeSettings/officePolicies)。
- **Office Intune** のポリシー: Intune 設定 カタログまたは管理用テンプレートを使用して、HKCU ポリシーを Windows 10 PC に展開する: デバイス構成プロファイルの [MEM](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/configurationProfiles)  \> 管理センターで。
  - ***管理用テンプレート***: 管理用テンプレートを構成するためにWindows 10手順 [を参照してください](/mem/intune/configuration/administrative-templates-windows)。
  - ***設定カタログ (プレビュー):*** カタログ (プレビュー) を使用する設定 [を参照してください](/mem/intune/configuration/settings-catalog)。
- **グループ ポリシー**: オンプレミスの Active Directory を使用して、グループ ポリシー オブジェクト (GPO) をユーザーとコンピューターに展開します。 この設定の GPO を作成するには、Microsoft 365 Apps for enterprise、Office 2019、および Office 2016 の最新の管理用テンプレート ファイル [(ADMX/ADML) と Office カスタマイズ ツールをダウンロード](https://www.microsoft.com/download/details.aspx?id=49030)します。

## <a name="known-issues"></a>既知の問題

- ポリシー **VBA** マクロ通知 (Access、PowerPoint、Visio、Word) またはマクロ **通知 (Excel**) が値に設定されている場合、デジタル署名されたマクロを除くすべて無効にすると、予期される信頼バーは表示されません。また、バックステージのセキュリティ情報は、設定が期待通り動作しているにもかかわらず、ブロックされたマクロの詳細を一覧表示しません。 チームOffice、この問題の解決に取り組む必要があります。

## <a name="admin-options-for-restricting-active-content"></a>アクティブ コンテンツを制限するための管理オプション

内部的に作成されたコンテンツと、ユーザーがインターネットからダウンロードするコンテンツに対する信頼のレベルには大きな違いがあります。 内部ドキュメントでアクティブ なコンテンツを許可し、インターネットからドキュメント内のアクティブ コンテンツをグローバルに許可することを検討してください。

ユーザーが特定の種類のアクティブ コンテンツを必要としない場合、最も安全なオプションは、ポリシーを使用して、そのアクティブ なコンテンツへのユーザー アクセスを無効にし、必要に応じて例外を許可する方法です。

次のポリシーを使用できます。

- **信頼できる場所をオフにする**: 利用可能なグループの例外。
- **信頼できるドキュメントをオフにする**: 使用可能なグループの例外。
- **すべてのアクティブ なコンテンツをオフにします**。個人の例外。

次のセクションの表では、アクティブ なコンテンツを制御する設定について説明します。 これらのポリシーは、ユーザーに適用される場合、信頼できるドキュメントに適用され、以前のエンド ユーザー エクスペリエンスは同じではない可能性があります。 また、この表には、推奨されるセキュリティ 基準設定が含まれています。また、上書きするユーザー プロンプトが使用可能な他の設定 (ユーザーがアクティブ なコンテンツを有効にできるように) を識別します。

### <a name="hkey_current_user-settings"></a>HKEY_CURRENT_USER設定

<p>

****
|カテゴリ|アプリ|ポリシー名|セキュリティベースライン<br>設定 (推奨)|ユーザー プロンプトを使用した設定<br>利用可能な上書き?|
|---|---|---|---|---|
|ActiveX|Office|ActiveXコントロールの初期化|**6**|**次の** 値に対してはい。 <ul><li>**3**</li><li>**4**</li><li>**5**</li><li>**6**</li></ul>|
|ActiveX|Office|Active X One Off フォームを許可する|**[Outlook のコントロールのみ読み込む]**|いいえ|
|ActiveX|Office|[ActiveX オブジェクトをチェックする]|セキュリティ基準設定ではありません。|いいえ|
|ActiveX|Office|すべての ActiveX を無効にする|セキュリティ基準設定ではありません。|**次の** 値に対してはい。 <ul><li>**Disabled**</li><li>**未構成**</li></ul>|
|ActiveX|Office|Forms3 でコントロールを読み込む|**1**|**次の** 値に対してはい。 <ul><li>**2**</li><li>**3**</li></ul>|
|アドインの機能拡張&機能拡張|Excel <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|署名されていないアプリケーション アドインの信頼バー通知を無効にしてブロックする|**Enabled (有効)**|**[は** い] の値が **[無効] です**。|
|アドインの機能拡張&機能拡張|Excel <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|アプリケーション アドインには信頼できる発行元による署名が必要|**Enabled (有効)**|いいえ|
|アドインの機能拡張&機能拡張|Excel|AutoRepublish 警告アラートを表示しない|**Disabled**|いいえ|
|アドインの機能拡張&機能拡張|Excel|WEBSERVICE 関数の通知設定|**通知ですべて無効にする**|**次の** 値に対してはい。 <ul><li>**通知ですべて無効にする**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドインの機能拡張&機能拡張|Office|発行済みOfficeサーバーをポーリングSharePointクライアントを無効にする|**Disabled**|いいえ|
|アドインの機能拡張&機能拡張|Office|ドキュメントおよびテンプレートによる UI の拡張を無効にする|Word で許可を解除する = True <p> [ファイルの許可をProject = False <p> [この値で許可Excel = True <p> [ユーザーの許可をVisio= False <p> [この値で許可PowerPoint = True <p> Access で許可を解除 = True <p> [ユーザーの許可をOutlook = True <p> [ユーザーの許可をPublisher = True <p> InfoPath で許可を解除する = True|いいえ|
|アドインの機能拡張&機能拡張|Outlook|[アドレス帳にアクセスするときの Outlook オブジェクト モデルに関する確認について構成する]|**自動拒否**|**次の** 値に対してはい。 <ul><li>**プロンプト ユーザー**</li><li>**コンピューター のセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドインの機能拡張&機能拡張|Outlook|オブジェクト Outlookプロンプトの構成 UserProperty オブジェクトの Formula プロパティにアクセスする場合|**自動拒否**|**次の** 値に対してはい。 <ul><li>**プロンプト ユーザー**</li><li>**コンピューター のセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドインの機能拡張&機能拡張|Outlook|[[名前を付けて保存] を実行するときの Outlook オブジェクト モデルに関する確認について構成する]|**自動拒否**|**次の** 値に対してはい。 <ul><li>**プロンプト ユーザー**</li><li>**コンピューター のセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドインの機能拡張&機能拡張|Outlook|[アドレス情報を読み込むときの Outlook オブジェクト モデルに関する確認について構成する]|**自動拒否**|**次の** 値に対してはい。 <ul><li>**プロンプト ユーザー**</li><li>**コンピューター のセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドインの機能拡張&機能拡張|Outlook|[会議出席依頼および仕事の依頼に返信するときの Outlook オブジェクト モデルに関する確認について構成する]|**自動拒否**|**次の** 値に対してはい。 <ul><li>**プロンプト ユーザー**</li><li>**コンピューター のセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドインの機能拡張&機能拡張|Outlook|[メール送信時の Outlook オブジェクト モデルに関する確認について構成する]|**自動拒否**|**次の** 値に対してはい。 <ul><li>**プロンプト ユーザー**</li><li>**コンピューター のセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドインの機能拡張&機能拡張|Outlook|オブジェクト Outlookカスタム アクション実行プロンプトを設定する|**自動拒否**|**次の** 値に対してはい。 <ul><li>**プロンプト ユーザー**</li><li>**コンピューター のセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドインの機能拡張&機能拡張|PowerPoint|プログラムの実行|**disable (プログラムを実行しない)**|**[は** い] の値 **を有効にする (実行前にユーザーに確認する)**|
|アドインの機能拡張&機能拡張|Word <p> Excel|スマート ドキュメントによるマニフェストの使用を無効にする|**Enabled (有効)**|いいえ|
|DDE|Excel|サーバーで動的データ Exchange (DDE) サーバーの起動を許可Excel|**Enabled (有効)**|**[は** い] の値が **[構成されていません] です**。|
|DDE|Excel|データベースで動的データ Exchange (DDE) サーバーの参照を許可Excel|**Enabled (有効)**|**次の** 値に対してはい。 <ul><li>**Disabled**</li><li>**未構成**</li></ul>|
|DDE|Word|動的データ Exchange|**Disabled**|いいえ|
|Jscript & VBScript|Outlook|[1 回限りの Outlook フォームでのスクリプトの使用を許可する]|**Disabled**|いいえ|
|Jscript & VBScript|Outlook|パブリック フォルダーに対Outlookオブジェクト モデル スクリプトの実行を許可しない|**Enabled (有効)**|いいえ|
|Jscript & VBScript|Outlook|共有フォルダーに対Outlookオブジェクト モデル スクリプトの実行を許可しない|**Enabled (有効)**|いいえ|
|マクロ|Excel|マクロ通知|**デジタル署名マクロを除くすべてのマクロを無効にする**|**次の** 値に対してはい。 <ul><li>**Disabled**</li><li>**未構成**</li></ul>|
|マクロ|Access <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|VBA マクロ通知設定|**デジタル署名マクロを除くすべてのマクロを無効にする** <p> and <p> **信頼できる発行元がマクロに署名する必要がある**|**次の** 値に対してはい。 <ul><li>**Disabled**</li><li>**未構成**</li></ul>|
|マクロ|Access <p> Excel <p> PowerPoint <p> Visio <p> Word|インターネットからファイル内でマクロOffice実行をブロックする|**Enabled (有効)**|**次の** 値に対してはい。 <ul><li>**Disabled**</li><li>**未構成**</li></ul>|
|マクロ|Excel|Open XML ブックで暗号化されたExcelスキャンする|**暗号化されたマクロをスキャンする (既定)**|いいえ|
|マクロ|Office|VBA で信頼されていないイントラネットの場所からのパスによる typelib 参照の読み込みを許可する|**Disabled**|いいえ|
|マクロ|Office|オートメーション セキュリティ|**[アプリケーションのマクロのセキュリティ レベルを適用する]**|いいえ|
|マクロ|Office|ローカル コンピューター上の安全でない場所を参照する可能性がある VBA ライブラリ参照の他のセキュリティ チェックを無効にする|**Disabled**|いいえ|
|マクロ|Office|マクロ ランタイム スキャン スコープ|**すべてのドキュメントを有効にする**|いいえ|
|マクロ|Office|V3 署名を使用する VBA マクロのみを信頼する|セキュリティ基準設定ではありません。|いいえ|
|マクロ|Outlook|Outlook セキュリティ モード|**セキュリティ Outlookポリシーを使用する**|GPO のすべての設定を有効にするにはOutlook必要です。 <p> 依存関係として言及されています (このポリシーは、アクティブ なコンテンツ自体をブロックしません)。|
|マクロ|Outlook|マクロのセキュリティ設定|**署名を警告する、署名されていないを無効にする**|**次の** 値に対してはい。 <ul><li>**常に警告する**</li><li>**署名を警告する、署名されていないを無効にする**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|マクロ|PowerPoint|Open XML プレゼンテーションで暗号化されたPowerPointスキャンする|**暗号化されたマクロをスキャンする (既定)**|いいえ|
|マクロ|発行者|Publisherオートメーション セキュリティ レベル|**選択 (確認)**|いいえ|
|マクロ|Word|Word Open XML ドキュメントで暗号化されたマクロをスキャンする|**暗号化されたマクロをスキャンする (既定)**|いいえ|
|

### <a name="hkey_local_machine-settings"></a>HKEY_LOCAL_MACHINE設定

<p>

****
|カテゴリ|アプリ|ポリシー名|セキュリティベースライン<br>設定 (推奨)|ユーザー プロンプトを使用した設定<br>利用可能な上書き?|
|---|---|---|---|---|
|ActiveX|Office|[ActiveX のインストールを制限する] |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|いいえ|
|アドインの機能拡張&機能拡張|Office|[アドオンの管理] |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|いいえ|
|アドインの機能拡張&機能拡張|Office|ドキュメントのフラッシュのアクティブ化をOfficeする|Com killbits の一覧については、「Microsoft セキュリティ ガイド ADMX/ADML ファイル」を参照して、アプリで Flash のすべてのライセンス認証をMicrosoft 365してください。 エンタープライズ セキュリティ ベースライン用の ADMX/ADML ファイルは、[セキュリティ コンプライアンス] ページ[Toolkit。](https://www.microsoft.com/download/details.aspx?id=55319)|いいえ|
|Jscript & VBScript|Office|従来のJScriptの実行をOffice|**有効**: <p> アクセス: 69632 <p> Excel: 69632 <p> OneNote: 69632 <p> Outlook: 69632 <p> PowerPoint: 69632 <p> Project: 69632 <p> Publisher: 69632 <p> Visio: 69632 <p> Word: 69632|いいえ|
|Jscript & VBScript|Office|[スクリプト化されたウィンドウのセキュリティ制限] |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|いいえ|
|

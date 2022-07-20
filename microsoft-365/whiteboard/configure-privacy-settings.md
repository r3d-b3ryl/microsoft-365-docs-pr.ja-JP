---
title: Microsoft Whiteboard でプライバシー設定を構成する
ms.author: chucked
author: chuckedmonson
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: コンプライアンスと、Microsoft Whiteboard でプライバシー設定を構成する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a2708d3eda92f3d29ea9ad6ee15e518d32d93a22
ms.sourcegitcommit: 49c275f78664740988bbc4ca4b14d3ad758e1468
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2022
ms.locfileid: "66882786"
---
# <a name="configure-privacy-settings-in-microsoft-whiteboard"></a>Microsoft Whiteboard でプライバシー設定を構成する

>[!NOTE]
> お客様またはユーザーが、既定のプライバシー設定、オプションの接続エクスペリエンス、診断データの収集方法について詳しく知りたい場合は、 [Microsoft Whiteboard のプライバシーとコンプライアンス](https://support.microsoft.com/office/privacy-and-compliance-ed9f0de9-71be-44c2-837d-e0f448660be1)に誘導します。

組織の Microsoft Whiteboard 管理者である場合は、次の操作を制御できます。

- ユーザーのデバイスで実行されている Whiteboard クライアント ソフトウェアについて、どのレベルの診断データが収集され、Microsoft に送信されます。

- Whiteboard のオプションの接続エクスペリエンスをユーザーが利用できるかどうか。

診断データのレベルを構成するには、管理者アカウントで[Microsoft 365 管理センター](/microsoft-365/admin/admin-overview/admin-center-overview?view=o365-worldwide)にサインインします。 管理センターのホーム ページで、[ **すべての>設定>組織の設定>ホワイトボードを表示する**] に移動します。

オプションの接続エクスペリエンスの可用性を構成するには、[Microsoft 365 Apps管理センター](https://config.office.com)で [Office クラウド ポリシー サービス](/deployoffice/admincenter/overview-office-cloud-policy-service)を使用します。 管理者アカウントでサインインし、 **カスタマイズ > ポリシー管理** に移動します。 構成するポリシーには、 **Office で追加のオプションの接続エクスペリエンスを使用できるようにする** という名前が付けられています。

## <a name="diagnostic-data-setting-for-your-organization"></a>組織の診断データ設定

組織内のデバイスで実行されている Whiteboard クライアント ソフトウェアについて Microsoft に収集および送信される診断データのレベルを選択できます。 オプションの診断データは、Microsoft 365 管理センターの設定を変更しない限り、Microsoft に送信されます。 オプションの診断データを送信するよう選択した場合は、必須の診断データも含まれています。

**必須** または **省略可能** に加えて、**どちらも選択しません**。 このオプションを選択した場合、ユーザーのデバイスで実行されている Whiteboard クライアント ソフトウェアに関する診断データは Microsoft に送信されません。 ただし、このオプションを使用すると、ユーザーが Whiteboard を使用しているときに発生する可能性がある問題を検出、診断、修復する Microsoft の機能が大幅に制限されます。

組織の資格情報 (職場または学校アカウントとも呼ばれる) を使用して Whiteboard にサインインしている場合、ユーザーはデバイスの診断データ レベルを変更できません。 ただし、個人の outlook.com メール アドレスなどの Microsoft アカウントを使用して Whiteboard にサインインしている場合は、[ **設定] > [プライバシーとセキュリティ]** に移動して、デバイスの診断データ レベルを変更できます。

## <a name="optional-connected-experiences-setting-for-your-organization"></a>組織のオプションの接続エクスペリエンス設定

Whiteboard でオプションの接続エクスペリエンスをユーザーが利用できるようにするかどうかを選択できます。 これらの接続エクスペリエンスは、Microsoft 365 管理センターで設定を変更しない限り、ユーザーが利用できます。 

この接続エクスペリエンスが違うのは、ユーザーの組織と Microsoft との商業契約の対象ではないためです。 オプションの接続エクスペリエンスは Microsoft がユーザーに直接提供しており、[オンライン サービス使用条件](https://www.microsoft.com/licensing/product-licensing/products)ではなく [Microsoft サービス規約](https://www.microsoft.com/servicesagreement)に準拠しています。

これらのオプションの接続エクスペリエンスをユーザーが利用できるように選択した場合でも、ユーザーは **[設定] > [プライバシーとセキュリティ]** に移動してグループとして無効にすることができます。 ユーザーは、組織の資格情報 (職場または学校アカウントとも呼ばれます) を使用して Whiteboard にサインインしている場合にのみ選択できます。個人の outlook.com メール アドレスなど、Microsoft アカウントでサインインしている場合は選択できません。

## <a name="required-diagnostic-data-events-collected-by-whiteboard"></a>Whiteboard によって収集された必要な診断データ イベント

各イベントのデータ フィールドの一覧を含め、Whiteboard によって収集される必要な診断データ イベントを次に示します。

**Intentional.CanvasObject.Ink.DrawFirstStroke**

初めて収集したインクが Microsoft Whiteboard のボードに追加されます。 この情報は、ボードへのインクの追加に関連するエラーをキャッチするために重要です。 Microsoft は、Microsoft Whiteboard が想定どおりに動作していることを保証するために、このデータを使用して問題を診断しています。

- **Action** – インク ストロークの種類
- **ソース** – インク ストロークの入力方法

**Intentional.SurfSide.ActivationProtocol.LoadFromUri**

Microsoft Whiteboard が別のアプリケーションまたはプロセスからの呼び出しによって起動されるたびに収集されます。 この情報は、別のアプリケーションまたはプロセスによって適切に呼び出されたときに Whiteboard が起動しないかどうかをキャッチするために重要です。 Microsoft は、Microsoft Whiteboard が想定どおりに動作していることを保証するために、このデータを使用して問題を診断しています。

- **ApplicationExecutionState** – アクティブ化プロトコルが発生したときのアプリの実行状態
- **IsSignedIn** – ユーザーは認証状態です
- **種類** - Whiteboard を起動するアプリケーションまたはプロセス

**Intentional.Whiteboard.Init.DisplayWhiteboard**

Microsoft Whiteboard がセッションごとにクライアントに実際に表示されるときに初めて収集されます。 この情報は、起動の問題をキャッチするために重要です。 Microsoft は、Microsoft Whiteboard が想定どおりに動作していることを保証するために、このデータを使用して問題を診断しています。

- **IsPrelaunched** – 起動前の状態
- **IsProtocolActivation** – アプリケーション起動の種類

**Intentional.Whiteboard.Init.StartApp**

前の状態がクラッシュせずに終了した後に Microsoft Whiteboard が起動するたびに収集されます。 この情報は、クラッシュする問題をキャッチするために重要です。 Microsoft は、Microsoft Whiteboard が想定どおりに動作していることを保証するために、このデータを使用して問題を診断しています。

- **First Start** - クライアントで初めてアプリが起動されました

**Intentional.Whiteboard.KeyCategory.UseCategory**

Microsoft Whiteboard のユーザー/セッション/ホワイトボードごとに、機能が初めて (および初めてのみ) 使用されるたびに収集されます。 この情報は、キー カテゴリが確実に使用されるようにするために重要です。 Microsoft は、Microsoft Whiteboard が想定どおりに動作していることを保証するために、このデータを使用して問題を診断しています。

- **CategoryName** – キー カテゴリの名前

**Intentional.Whiteboard.KeyFeature.UseFeature**

Microsoft Whiteboard のユーザー/セッション/ホワイトボードごとに、機能が初めて (および初めてのみ) 使用されるたびに収集されます。 この情報は、機能が呼び出されて使用されるようにするために重要です。 Microsoft は、Microsoft Whiteboard が想定どおりに動作していることを保証するために、このデータを使用して問題を診断しています。

- **FeatureName** – キー機能の名前

**Intentional.Whiteboard.SafeBoot.StartApp**

前回の状態がクラッシュに終わった後に Microsoft Whiteboard が起動するたびに収集されます。 この情報は、クラッシュする問題をキャッチするために重要です。 Microsoft は、Microsoft Whiteboard が想定どおりに動作していることを保証するために、このデータを使用して問題を診断しています。

- **First Start** - クライアントで初めてアプリが起動されました

**Intentional.Whiteboard.スクラブ.LoadSettings**

Microsoft Whiteboard が起動するたびに収集されます。 この情報は、ユーザー構成の設定に関連するエラーをキャッチするために重要です。 Microsoft は、Microsoft Whiteboard が想定どおりに動作していることを保証するために、このデータを使用して問題を診断しています。

- **ActivePen** – ペン モードの状態
- **CollectFullTelemetryWithoutSignIn** – サインインの有効化のない完全なテレメトリ コレクション
- **DefaultWhiteboardBackgroundColor** – 既定のボードの背景色
- **DefaultWhiteboardBackgroundPattern** – 既定のボードの背景パターン
- **FlightStatus** – フライトの状態
- **InkToShape** – インクから図形への有効化
- **InkToTable** – テーブルへのインクの有効化
- **SignInEnabled** – ユーザー サインインの有効化
- **SharingWithoutSignInEnabled** – 共有ボードの有効化
- **ToolbarLocation** – 画面上の既定のツール バーの場所
- **TeamSettingsSource** – Teams 設定の有効化

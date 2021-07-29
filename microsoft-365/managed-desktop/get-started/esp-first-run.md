---
title: Autopilot と登録ステータス ページの初回実行時エクスペリエンス
description: ESP エクスペリエンス、使用する設定、および構成の変更を展開する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 99bfaf40ab2bce2878af76650f92dda9f528be59
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53622114"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Autopilot と登録ステータス ページの初回実行時エクスペリエンス

Microsoft マネージド デスクトップ[は、Windows](/windows/deployment/windows-autopilot/windows-autopilot)と Microsoft Intuneの登録状態ページ[(ESP)](/windows/deployment/windows-autopilot/enrollment-status)の両方を使用して、可能な限り最高の初回実行エクスペリエンスをユーザーに提供します。

## <a name="initial-deployment"></a>初期展開

ESP エクスペリエンスを提供するには、デバイスをサービスに登録Microsoft マネージド デスクトップがあります。 登録の詳細については、「新[](../get-started/register-devices-self.md)しいデバイスを自分で登録する」または「デバイスを登録する[パートナー向け手順」を参照してください](../get-started/register-devices-partner.md)。
事前プロビジョニングされた展開の登録状態ページと自動パイロットは、既定で Microsoft マネージド デスクトップ。

## <a name="autopilot-profile-settings"></a>Autopilot プロファイルの設定

Microsoft マネージド デスクトップユーザーのデバイスに使用される Autopilot プロファイルで次の設定を使用します。

<br>

****

|設定|値|
|---|---|
|展開モード|ユーザー 駆動型|
|Azure ADに参加する|Azure AD参加|
|言語 (地域)|ユーザーの選択|
|キーボードを自動的に構成する|いいえ|
|Microsoft ソフトウェア ライセンス条項|非表示|
|プライバシー設定|非表示|
|アカウントの変更オプションを非表示にする|Show|
|ユーザー アカウントの種類|Standard|
|Allow White Glove OOBE|はい|
|デバイス名テンプレートの適用|はい|
|名前を入力する|MMD-%RAND:11%|
|

## <a name="enrollment-status-page-settings"></a>登録状態ページの設定

Microsoft マネージド デスクトップは、次の設定を [登録状態ページ] エクスペリエンスに使用します。

<br>

****

|設定|値|
|---|---|
|アプリとプロファイルの構成の進行状況を表示する|はい|
|インストール時間が指定した分数より長い場合にエラーを表示する|60|
|制限時間エラーが発生した場合にカスタム メッセージを表示する|いいえ|
|インストール エラーに関するログの収集をユーザーに許可する|はい|
|ページを既定のエクスペリエンス (OOBE) によってプロビジョニングされたデバイスにのみ表示する|はい|
|すべてのアプリとプロファイルがインストールされるまでデバイスの使用をブロックする|はい|
|インストール エラーが発生した場合、ユーザーにデバイスのリセットを許可する|はい|
|インストール エラーが発生した場合、ユーザーにデバイスの使用を許可する|はい|
|ユーザー/デバイスに割り当てられている場合、これらの必須アプリがインストールされるまでデバイスの使用をブロックする|モダン ワークプレース - 時間の修正|モダン ワークプレース - クライアント ライブラリ|
|

登録状態ページのエクスペリエンスは、3 つのフェーズで発生します。 詳細については、「登録状態 [ページの追跡情報」を参照してください](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)。

エクスペリエンスは次のように進みます。

1. 自動パイロット エクスペリエンスが開始され、ユーザーは資格情報を入力します。
2. デバイスが [登録状態] ページを開き、[デバイスの準備] フェーズと [デバイスセットアップ] フェーズに進みます。 ユーザー ESP が無効になっているため、3 番目の手順 (アカウントのセットアップ) は現在、Microsoft マネージド デスクトップ構成でスキップされています。 デバイスが再起動します。
3. 再起動後、デバイスは他のユーザー Windowsサインイン ページを **開きます**。
4. ユーザーが資格情報を再度入力すると、デスクトップが開きます。

> [!NOTE]
> Win32 アプリは、新しいバージョンが 1903 以降Windows 10 ESP 中にのみ展開されます。

![「デバイスの準備」フェーズと「デバイスセットアップ」フェーズを示す自動パイロットセットアップのスタート ページ。](../../media/mmd-autopilot-screenshot.png)


## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a>事前プロビジョニングされた展開のための Autopilot のその他の前提条件

- デバイスに有線ネットワーク接続が必要です。
- 2020 年 8 月より前に Microsoft マネージド デスクトップポータルを使用して登録されているデバイスがある場合は、登録を取りやめて再度登録します。
- デバイスには、2020 年 11 月の累積的な更新プログラム[19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3)または[20H1 2020.11C](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e)を含むファクトリ イメージが必要です。または最新の Microsoft マネージド デスクトップ イメージでイメージを再作成する必要があります。
- 物理デバイスは、TPM 2.0 とデバイス構成証明をサポートしている必要があります。 仮想マシンはサポートされていません。 事前プロビジョニング プロセスでは、Windows自動パイロットの自己展開機能が使用されます。そのため、TPM 2.0 が必要です。 また、TPM 構成証明プロセスでは、TPM プロバイダーごとに一意の HTTPS URL のセットにアクセスする必要があります。 詳細については、「Autopilot の自己展開モード」および「Autopilot の事前プロビジョニングされた展開」のエントリを参照Windows[してください。](/mem/autopilot/networking-requirements#tpm)

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a>事前プロビジョニングされた展開用の Autopilot の一連のイベント

1. IT 管理者は、必要に応じてデバイスを再イメージ化またはリセットします。
2. IT 管理者は、デバイスを起動し、アウトオブボックス エクスペリエンスに達し、Windowsキーを 5 回押します。
3. IT 管理者は、自動パイロット Windowsを選択し、[続行] を **選択します**。 [自動操縦Windows画面で、デバイスに関する情報が表示されます。
4. IT 管理者が [ **プロビジョニング] を選択** してプロビジョニング プロセスを開始します。
5. デバイスは ESP を開始し、デバイスの準備とセットアップのフェーズを実行します。 デバイスのセットアップ フェーズでは、アプリのインストール **x が表示** されます (ESP プロファイルの正確な構成に応じて)。
6. ユーザー ESP を無効にしたので、アカウントのセットアップ 手順は現在、Microsoft マネージド デスクトップ構成でスキップされます。
7. デバイスが再起動します。

再起動すると、デバイスに緑色の状態画面が表示されます。[再シール] ボタン **が表示** されます。

> [!IMPORTANT]
> 既知の問題:
>
> - 事前プロビジョニングされた展開の再シール関数の Autopilot の後、ESP は再び実行されません。
> - 事前プロビジョニングされた展開では、デバイスの名前が Autopilot によって変更されません。 デバイスの名前は、ESP ユーザー フローを通過した後にのみ変更されます。

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>自動操縦と登録の状態ページの設定に変更する

ユーザーが使用するセットアップMicrosoft マネージド デスクトップニーズと完全に一致しない場合は、管理ポータルを使用してサポート チケットを[ファイルできます](https://portal.azure.com/)。 必要な構成の種類の例を次に示します。

### <a name="autopilot-settings-change"></a>自動操縦設定の変更

別のデバイス名テンプレートを要求する場合があります。 ただし、展開モード、Join to Azure AD As、Privacy 設定、またはユーザー アカウントの種類を変更することはできません。

### <a name="enrollment-status-page-settings-change"></a>登録状態ページの設定の変更

- "インストールに指定した分数より長い時間がかかる場合にエラーを表示する" 設定の分数が長くなります。
- 表示されるエラー メッセージ。
- [ユーザー/デバイスに割り当てられている場合、必要なアプリがインストールされるまでデバイスの使用をブロックする] 設定でアプリケーションを追加または削除します。

## <a name="required-applications"></a>必須のアプリケーション

- モダン ワークプレース デバイス グループのテスト、First、Fast、および Broad でアプリケーションをターゲットに設定する必要があります。 アプリケーションは、"System" コンテキストにインストールする必要があります。 すべてのグループに割り当てる前に、テスト グループで ESP によるテストを完了してください。
- デバイスを再起動する必要があるアプリケーションはありません。 再起動が必要な場合は、アプリケーション パッケージをビルドするときに、アプリケーションを "何もしない" に設定することをお勧めします。
- 必要なアプリケーションを、ユーザーがデバイスにサインインするときにすぐに必要なコア アプリケーションにのみ制限します。
- アプリケーションのインストール フェーズ中にタイムアウトを回避するには、すべてのアプリケーションの合計サイズをまとめて 1 GB 以下にしてください。
- 理想的には、アプリには依存関係を持つ必要があります。 依存関係が必要 *なアプリがある* 場合は、ESP 評価の一環としてアプリを構成、テスト、検証してください。
- Microsoft Teams ESP に含めません。

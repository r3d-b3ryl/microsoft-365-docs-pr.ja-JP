---
title: Autopilot と登録ステータス ページの初回実行時エクスペリエンス
description: ESP の使用方法、使用した設定、および構成の変更を展開する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e2340c7c0bf00165bb43740d3d095b5b0402fc0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126627"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Autopilot と登録ステータス ページの初回実行時エクスペリエンス

Microsoft マネージドデスクトップでは、 [Windows 自動操縦](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) と microsoft Intune の [登録状態ページ (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) の両方を使用して、ユーザーに最適な最初の実行環境を提供します。

[登録の状態] ページは、現在パブリックプレビューにあります。

## <a name="initial-deployment"></a>初期展開

ESP の動作を提供するには、Microsoft Managed Desktop service でデバイスを登録する必要があります。 登録の詳細については、「 [新しいデバイスを自分で登録](../get-started/register-devices-self.md) する」または「 [パートナーがデバイスを登録するための手順](../get-started/register-devices-partner.md)」を参照してください。

デバイスがサービスに登録されたら、 [管理者ポータル](https://portal.azure.com/)を使用してサポートチケットを提出することによって、Microsoft マネージドデスクトップデバイスの ESP を有効にすることができます。 最初に、チケットをファイル化するときに、ESP 構成をテストグループに展開します。 このグループは、24時間ごとに展開された他のグループ (最初、高速、広範) に展開されます。 展開を一時停止するには、別のチケットをファイルに保存する操作を要求します。

## <a name="autopilot-profile-settings"></a>自動操縦プロファイルの設定

Microsoft マネージドデスクトップでは、ユーザーのデバイスに使用する自動操縦プロファイルでこれらの設定を使用します。


|Setting  |値  |
|---------|---------|
|展開モード |  ユーザー主導       |
|Azure AD に参加する     |  Azure AD 参加済み       |
|言語 (地域)     | オペレーティングシステムの既定値        |
|キーボードの自動構成     | いいえ        |
|マイクロソフトソフトウェアライセンス条項     |  非表示       |
|プライバシーの設定     | 非表示        |
|アカウントの変更オプションを非表示にする     | Show        |
|ユーザーアカウントの種類     |  Standard       |
|白色のグローブ OOBE を許可する     |  はい       |
|デバイス名テンプレートの適用     | はい        |
|名前を入力してください     | MMD-% RAND: 11%        |

> [!NOTE]
> 「白の手袋」プロビジョニングは、ESP が有効になっているお客様に対してのみ有効になっていますが、Microsoft マネージドデスクトップでは現在サポートされていません。

## <a name="enrollment-status-page-settings"></a>登録の状態ページの設定

Microsoft マネージドデスクトップは、次の設定を使用して登録の状態のページの機能を使用します。


|Setting  |値  |
|---------|---------|
|アプリとプロファイルの構成の進行状況を表示する     | はい        |
|インストール時に指定した分数を超える時間が発生した場合にエラーを表示する     |  60       |
|時間制限エラーが発生した場合にカスタムメッセージを表示する     |  はい       |
|エラー メッセージ     | はい。デバイスのセットアップには、予想よりも少し時間がかかります。 開始するには以下をクリックしてください。バックグラウンドで設定を完了します        |
|ユーザーがインストールエラーに関するログを収集できるようにする     |  はい       |
|[すぐにプロビジョニングされたデバイスにのみページを表示する (OOBE)]     | はい        |
|すべてのアプリとプロファイルがインストールされるまで、デバイスの使用をブロックする     |  はい       |
|インストールエラーが発生した場合にユーザーがデバイスをリセットすることを許可する     |  はい       |
|インストールエラーが発生した場合にユーザーにデバイスの使用を許可する     |  はい       |
|ユーザー/デバイスに割り当てられている場合は、これらの必要なアプリがインストールされるまで、デバイスを使用することを禁止します。     |  モダンタイムプレース修正       |



登録の状態のページの動作は、3つのフェーズで行われます。 詳細については、「 [登録ステータスページの追跡情報](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)」を参照してください。

この作業は次のように進めます。

1. 自動操縦作業が開始され、ユーザーが資格情報を入力します。
2. デバイスが [登録の状態] ページを開き、デバイスの準備とデバイスのセットアップフェーズを続行します。 3番目の手順 (アカウントのセットアップ) は、ユーザーの ESP が無効になっているため、Microsoft マネージドデスクトップの構成で *現在スキップ* されています。 デバイスが再起動します。
3. 再起動した後、デバイスによって Windows サインインページが **他のユーザー** と共に開かれます。
4. ユーザーが資格情報をもう一度入力すると、デスクトップが開きます。

> [!NOTE]
> Win32 アプリは、Windows 10 のバージョンが1903以降の場合にのみ ESP の間に展開されます。

![「デバイスの準備」と「デバイスのセットアップ」のフェーズが表示されている自動操縦のセットアップの開始ページです。](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a>白いグローブプロビジョニング

Microsoft Managed Desktop は現在、Windows 自動操縦の "白のグローブ" 機能をサポートしていません。

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>自動操縦と登録の状態のページ設定に変更する

Microsoft マネージドデスクトップで使用されているセットアップがニーズに正確に一致しない場合は、 [管理ポータル](https://portal.azure.com/)を使用してサポートチケットをファイルにすることができます。 必要な構成の種類の例を次に示します。

### <a name="autopilot-settings-change"></a>自動操縦設定の変更

別のデバイス名テンプレートを要求することもできます。 ただし、[展開モードの変更]、[Azure AD に参加]、[プライバシー設定]、または [ユーザーアカウントの種類] には変更できません。

### <a name="enrollment-status-page-settings-change"></a>登録の状態ページの設定の変更

- "インストール時に指定した時間より長く時間が経過した場合にエラーを表示する" 設定の時間を長くします。
- 表示されるエラーメッセージ
- "ブロックデバイスでのアプリケーションの追加または削除は、これらの必要なアプリがユーザー/デバイスに割り当てられている場合にインストールされるようにする" 設定にします。

## <a name="required-applications"></a>必要なアプリケーション

- モダン Workplace *device groups* テスト、ファースト、Fast、および広範なアプリケーションで、アプリケーションを対象とする必要があります。 アプリケーションは、"System" コンテキストにインストールする必要があります。 テストグループ内の ESP でテストを完了してから、すべてのグループに割り当てる必要があります。
- アプリケーションでデバイスを再起動する必要はありません。 アプリケーションパッケージを再起動する必要がある場合は、アプリケーションパッケージの作成時にアプリケーションを "実行しない" に設定することをお勧めします。
- 必要なアプリケーションを、ユーザーがデバイスにサインインするときにすぐに必要とするコアアプリケーションのみに制限します。
- アプリケーションのインストール段階でタイムアウトが発生しないように、すべてのアプリケーションの合計サイズを 1 GB 以下にまとめておきます。
- アプリが依存関係を持たないことが理想的です。 依存関係が *必要* なアプリがある場合は、ESP 評価の一部として構成、テスト、検証を行うようにしてください。
- "User" コンテキスト (Teams など) を必要とするアプリケーションは、ESP のパブリックプレビューに含めることはできません。

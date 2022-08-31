---
title: Microsoft Defender ウイルス対策保護機能を有効にして構成する
description: 動作の監視、ヒューリスティック、機械学習などの Microsoft Defender ウイルス対策のリアルタイム保護機能を有効にして構成する
keywords: ウイルス対策, リアルタイム保護, rtp, 機械学習, 動作監視, ヒューリスティック
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.date: 10/22/2021
manager: dansimp
ms.custom: nextgen
ms.collection: M365-security-compliance
ms.openlocfilehash: c8137314b845699ec98b5424fa5942ef484f2537
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479800"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a>グループ ポリシーで Microsoft Defender ウイルス対策を常時保護を有効にして構成する

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

常時オン保護は、既知の不審なアクティビティや悪意のあるアクティビティに基づいてマルウェアを識別するためのリアルタイムの保護、動作監視、ヒューリスティックで構成されます。

これらのアクティビティには、既存のファイルに対して異常な変更を加えるプロセス、自動スタートアップ レジストリ キーの変更または作成、スタートアップの場所 (自動起動機能拡張ポイント、ASEPs とも呼ばれます)、ファイル システムまたはファイル構造に対するその他の変更などのイベントが含まれます。

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a>グループ ポリシーで常時オン保護を有効にして構成する

**ローカル グループ ポリシー エディター** を使用して、Microsoft Defender ウイルス対策の常時オン保護設定を有効にして構成できます。

常時オン保護を有効にして構成するには:

1. **次のように、ローカル グループ ポリシー エディター** を開きます。

    1. Windows 10またはタスク バー検索ボックスWindows 11、「**gpedit**」と入力します。

    2. [**ベスト マッチ**] で、[**グループ ポリシーの編集]** を選択して **ローカル グループ ポリシー エディター** を起動します。
    
       :::image type="content" source="images/gpedit-search.png" alt-text="コントロール パネルの GPEdit タスク バーの検索結果" lightbox="images/gpedit-search.png":::

2. **ローカル グループ ポリシー エディター** の左側のウィンドウで、ツリーを [**コンピューター構成** \> **管理用テンプレート** \> **] Windows コンポーネント** \> **の Microsoft Defender ウイルス対策** に展開します。

3. Microsoft Defender ウイルス対策マルウェア対策サービス ポリシー設定を構成します。

   右側の **[Microsoft Defender ウイルス対策** の詳細] ウィンドウで、[ **通常の優先度で起動するマルウェア対策サービスを許可** する] をダブルクリックし、[ **有効]** に設定します。

   次に [**OK**] を選びます。

4. 次のように、Microsoft Defender ウイルス対策のリアルタイム保護ポリシー設定を構成します。

    1. **Microsoft Defender ウイルス対策** の詳細ウィンドウで、[**リアルタイム保護**] をダブルクリックします。 または、左側のウィンドウの **Microsoft Defender ウイルス対策** ツリーで、[ **リアルタイム保護**] を選択します。

    2. 右側の **[リアルタイム保護** の詳細] ウィンドウで、リアルタイム [保護ポリシー](#real-time-protection-policy-settings) 設定で指定されているポリシー設定をダブルクリックします (この記事の後半)。

    3. 必要に応じて設定を構成し、[OK] を選択 **します**。

    4. テーブル内の各設定について、前の手順を繰り返します。

5. 次のように、Microsoft Defender ウイルス対策スキャン ポリシー設定を構成します。

    1. 左側のウィンドウの **Microsoft Defender ウイルス対策** ツリーで、[ **スキャン**] を選択します。
    
   2. 右側の [ **スキャン** の詳細] ウィンドウで、[ **ヒューリスティックを有効にする**] をダブルクリックし、[ **有効]** に設定します。 

   3. **[OK]** を選択します。

6. **ローカル グループ ポリシー エディター** を閉じます。

### <a name="real-time-protection-policy-settings"></a>リアルタイム保護ポリシー設定

|Setting|既定の設定|
|---|---|
|動作の監視を有効にする <p> ウイルス対策エンジンは、疑わしい既知の悪意のあるアクティビティがないか、エンドポイント上のファイル プロセス、ファイルとレジストリの変更、その他のイベントを監視します。|有効|
|ダウンロードしたすべてのファイルと添付ファイルをスキャンする <p> ダウンロードしたファイルと添付ファイルは自動的にスキャンされます。 このスキャンは、ダウンロード前とダウンロード中にファイルをスキャンするWindows Defender SmartScreen フィルターに加えて動作します。|有効|
|コンピューター上のファイルとプログラムのアクティビティを監視する <p> Microsoft Defender ウイルス対策エンジンは、ファイルの変更 (ファイルの書き込み (移動、コピー、変更など) と一般的なプログラム アクティビティ (開いているプログラムや実行中のプログラム、その他のプログラムの実行を引き起こすプログラム) をメモします。|有効|
|未加工ボリューム書き込み通知を有効にする <p> 未加工ボリュームの書き込みに関する情報は、動作監視によって分析されます。|Enabled|
|リアルタイム保護が有効になっている場合は必ずプロセス スキャンを有効にする <p> Microsoft Defender ウイルス対策エンジンを個別に有効にして、実行中のプロセスをスキャンして、疑わしい変更や動作を行うことができます。 これは、リアルタイム保護を一時的に無効にし、無効になっている間に開始されたプロセスを自動的にスキャンする場合に便利です。|有効|
|スキャンするダウンロードしたファイルと添付ファイルの最大サイズを定義する <p> サイズはキロバイト単位で定義できます。|Enabled|
|動作の監視を有効にするためのローカル設定のオーバーライドを構成する <p> 動作監視の構成に対してローカル オーバーライドを構成します。 この設定は、グループ ポリシーでのみ設定できます。 この設定を有効にすると、ローカル設定がグループ ポリシーよりも優先されます。 この設定を無効にするか、未構成にした場合、グループ ポリシーはローカル環境設定よりも優先されます。|Enabled|
|ダウンロードしたすべてのファイルと添付ファイルをスキャンするためのローカル設定のオーバーライドを構成する <p> ダウンロードしたすべてのファイルと添付ファイルのスキャンを構成するためのローカル オーバーライドを構成します。 この設定は、グループ ポリシーでのみ設定できます。 この設定を有効にすると、ローカル設定がグループ ポリシーよりも優先されます。 この設定を無効にするか、未構成にした場合、グループ ポリシーはローカル環境設定よりも優先されます。|Enabled|
|コンピューター上のファイルとプログラムのアクティビティを監視するためのローカル設定のオーバーライドを構成する <p> コンピューター上のファイルとプログラムのアクティビティを監視する構成のローカル オーバーライドを構成します。 この設定は、グループ ポリシーでのみ設定できます。 この設定を有効にすると、ローカル設定がグループ ポリシーよりも優先されます。 この設定を無効にするか、未構成にした場合、グループ ポリシーはローカル環境設定よりも優先されます。|Enabled|
|リアルタイム保護を有効にするローカル設定のオーバーライドを構成する <p> リアルタイム保護を有効にするために、構成のローカル オーバーライドを構成します。 この設定は、グループ ポリシーでのみ設定できます。 この設定を有効にすると、ローカル設定がグループ ポリシーよりも優先されます。 この設定を無効にするか、未構成にした場合、グループ ポリシーはローカル環境設定よりも優先されます。|Enabled|
|受信および送信ファイル アクティビティを監視するためのローカル設定のオーバーライドを構成する <p> 受信および送信ファイル アクティビティの監視の構成に対してローカル オーバーライドを構成します。 この設定は、グループ ポリシーでのみ設定できます。 この設定を有効にすると、ローカル設定がグループ ポリシーよりも優先されます。 この設定を無効にするか、未構成にした場合、グループ ポリシーはローカル環境設定よりも優先されます。|Enabled|
|受信および送信ファイルとプログラム アクティビティの監視を構成する <p> 受信方向、送信方向、両方向、または両方向で監視を行う必要があるかどうかを指定します。 この操作は、特定のサーバーまたはサーバーの役割を定義し、大量のファイル変更を 1 方向のみに表示し、ネットワーク パフォーマンスを向上させる Windows Server インストールに関連します。 ネットワーク上の完全に更新されたエンドポイント (およびサーバー) では、ファイル変更の数や方向に関係なく、パフォーマンスへの影響はほとんどありません。|有効 (両方向)|

## <a name="disable-real-time-protection-in-group-policy"></a>グループ ポリシーでリアルタイム保護を無効にする

> [!WARNING]
> リアルタイム保護を無効にすると、エンドポイントの保護が大幅に減り、推奨されません。

メインのリアルタイム保護機能は既定で有効になっていますが、**ローカル グループ ポリシー エディター** を使用して無効にすることができます。

### <a name="to-disable-real-time-protection-in-group-policy"></a>グループ ポリシーでリアルタイム保護を無効にするには

1. **ローカル グループ ポリシー エディターを開きます**。

   1. Windows 10またはタスク バー検索ボックスWindows 11、「**gpedit**」と入力します。
   2. [**ベスト マッチ**] で、[**グループ ポリシーの編集]** を選択して **ローカル グループ ポリシー エディター** を起動します。

2. **ローカル グループ ポリシー エディター** の左側のウィンドウで、ツリーを [**コンピューター構成** \> **管理用テンプレート** \> **] Windows コンポーネント** \> **の Microsoft Defender ウイルス対策** \> **リアルタイム保護** に展開します。

3. 右側の **[リアルタイム保護** の詳細] ウィンドウで、[ **リアルタイム保護を無効にする**] をダブルクリックします。

4. [ **リアルタイム保護設定をオフにする]** ウィンドウで、オプションを **[有効]** に設定します。
   
5. [**OK**] を選択します。

6. **ローカル グループ ポリシー エディター** を閉じます。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [行動、ヒューリスティック、リアルタイム保護を構成する](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)

---
title: イベント ビューアーを使用してイベントとエラーを確認する
description: Microsoft Defender for Endpoint サービスによって報告されたすべてのイベントの説明とトラブルシューティング手順 (必要に応じて) を取得します。
keywords: トラブルシューティング、イベント ビューアー、ログの概要、エラー コード、失敗した、Microsoft Defender for Endpoint Service、開始できない、壊れている、開始できない
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933843"
---
# <a name="review-events-and-errors-using-event-viewer"></a>イベント ビューアーを使用してイベントとエラーを確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- イベント ビューアー
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

イベントの ID は、個々のデバイスの [イベント ビューアー](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) で確認できます。

たとえば、[デバイス] リストにデバイスが表示されない場合は、デバイスでイベントの ID を探す必要がある場合があります。 次に、この表を使用して、さらにトラブルシューティングの手順を決定できます。

**イベント ビューアーを開き、Microsoft Defender for Endpoint サービス イベント ログを検索します。**

1. **[Windows] メニューの**[スタート] をクリックし、「イベント ビューアー」**と入力し**、Enter キーを **押します**。

2. ログ リストの [ログの概要 **] で****、Microsoft-Windows-SENSE/Operational が表示されるまでスクロールします**。 アイテムをダブルクリックしてログを開きます。

   a.  [アプリケーションとサービス ログ] Microsoft Windows SENSE を展開して [操作] をクリックして、ログ  >    >    >  に **アクセスすることもできます**。

   > [!NOTE]
   > SENSE は、Microsoft Defender for Endpoint をサポートする動作センサーを参照するために使用される内部名です。

3. サービスによって記録されたイベントがログに表示されます。 サービスによって記録されるイベントの一覧については、次の表を参照してください。

<table>
<tbody style="vertical-align:top;">
<tr>
<th>イベント ID</th>
<th>メッセージ</th>
<th>説明</th>
<th>Action</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft Defender for Endpoint service が開始されました (バージョン <code>variable</code> )。</td>
<td>システムの起動時、シャットダウン中、オンボーディング中に発生します。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>2</td>
<td>Microsoft Defender for Endpoint service shutdown.</td>
<td>デバイスがシャットダウンまたはオフボードされている場合に発生します。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>3</td>
<td>Microsoft Defender for Endpoint service の開始に失敗しました。 エラー コード: <code>variable</code> .</td>
<td>サービスが開始しなかった。</td>
<td>他のメッセージを確認して、考えられる原因とトラブルシューティングの手順を確認します。</td>
</tr>
<tr>
<td>4</td>
<td>Microsoft Defender for Endpoint service がでサーバーに連絡しました <code>variable</code> 。</td>
<td>Variable = Defender for Endpoint 処理サーバーの URL。<br>
この URL は、ファイアウォールまたはネットワーク アクティビティに表示される URL と一致します。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>5</td>
<td>Microsoft Defender for Endpoint service でサーバーへの接続に失敗しました <code>variable</code> 。</td>
<td>Variable = Defender for Endpoint 処理サーバーの URL。<br>
サービスは、その URL の外部処理サーバーに接続できません。</td>
<td>URL への接続を確認します。 「Configure <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">proxy and Internet connectivity」を参照してください</a>。</td>
</tr>
<tr>
<td>6</td>
<td>Microsoft Defender for Endpoint Service はオンボードされていないので、オンボーディング パラメーターが見つかりませんでした。</td>
<td>デバイスが正しくオンボードされていないので、ポータルに報告されません。</td>
<td>サービスを開始する前にオンボーディングを実行する必要があります。<br>
オンボーディング設定とスクリプトが適切に展開されていることを確認します。 構成パッケージを再展開してみてください。<br>
「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</td>
</tr>
<tr>
<td>7</td>
<td>Microsoft Defender for Endpoint service では、オンボーディング パラメーターの読み取りが失敗しました。 失敗: <code>variable</code> .</td>
<td>変数 = 詳細なエラーの説明。 デバイスが正しくオンボードされていないので、ポータルに報告されません。</td>
<td>オンボーディング設定とスクリプトが適切に展開されていることを確認します。 構成パッケージを再展開してみてください。<br>
「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</td>
</tr>
<tr>
<td>8</td>
<td>Microsoft Defender for Endpoint service では、構成のクリーンアップに失敗しました。 エラー コード: <code>variable</code> .</td>
<td><b>オンボーディング中:</b> サービスは、オンボーディング中に構成のクリーンアップに失敗しました。 オンボーディング プロセスは続行されます。 <br><br> <b>オフボード中:</b> サービスは、オフボード中に構成のクリーンアップに失敗しました。 オフボード プロセスは終了しましたが、サービスは実行を続ける。
 </td>
<td><b>オンボーディング:</b> アクションは不要です。 <br><br> <b>オフボード:</b> システムを再起動します。<br>
「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</td>
</tr>
<tr>
<td>9</td>
<td>Microsoft Defender for Endpoint service は、開始の種類を変更できなかった。 エラー コード: <code>variable</code> .</td>
<td><b>オンボーディング中:</b> デバイスが正しくオンボードされていないので、ポータルに報告されません。 <br><br><b>オフボード中:</b> サービスの開始の種類を変更できなかった。 オフボードプロセスは続行されます。 </td>
<td>オンボーディング設定とスクリプトが適切に展開されていることを確認します。 構成パッケージを再展開してみてください。<br>
「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</td>
</tr>
<tr>
<td>10</td>
<td>Microsoft Defender for Endpoint Service は、オンボーディング情報を保持できなかった。 エラー コード: <code>variable</code> .</td>
<td>デバイスが正しくオンボードされていないので、ポータルに報告されません。</td>
<td>オンボーディング設定とスクリプトが適切に展開されていることを確認します。 構成パッケージを再展開してみてください。<br>
「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</td>
</tr>
<tr>
<td>11</td>
<td>Defender for Endpoint サービスのオンボーディングまたは再オンボーディングが完了しました。</td>
<td>デバイスが正しくオンボードされました。</td>
<td>通常の動作通知。アクションは必要ありません。<br>
デバイスがポータルに表示されるには数時間かかる場合があります。</td>
</tr>
<tr>
<td>12 </td>
<td>Microsoft Defender for Endpoint では、既定の構成の適用に失敗しました。</td>
<td>サービスが既定の構成を適用できなかった。</td>
<td>このエラーは、短時間で解決する必要があります。</td>
</tr>
<tr>
<td>13</td>
<td>Microsoft Defender for Endpoint デバイス ID が計算 <code>variable</code> されます。</td>
<td>通常の操作プロセス。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>15 </td>
<td>エンドポイントの Microsoft Defender は、URL を使用してコマンド チャネルを開始できません <code>variable</code> 。</td>
<td>Variable = Defender for Endpoint 処理サーバーの URL。<br>
サービスは、その URL の外部処理サーバーに接続できません。</td>
<td>URL への接続を確認します。 「Configure <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">proxy and Internet connectivity」を参照してください</a>。</td>
</tr>
<tr>
<td>17 </td>
<td>Microsoft Defender for Endpoint service は、接続されたユーザー エクスペリエンスとテレメトリ サービスの場所を変更できなかった。 エラー コード: <code>variable</code> .</td>
<td>Windows テレメトリ サービスでエラーが発生しました。</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">診断データ サービスが有効になっているか確認します</a>。<br>
オンボーディング設定とスクリプトが適切に展開されていることを確認します。 構成パッケージを再展開してみてください。<br>
「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</td>
</tr>
<tr>
<td>18 </td>
<td>OOBE (Windows ようこそ) が完了しました。</td>
<td>サービスは、Windows 更新プログラムのインストールが完了した後にのみ開始されます。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>19</td>
<td>OOBE (Windows ようこそ) がまだ完了していません。</td>
<td>サービスは、Windows 更新プログラムのインストールが完了した後にのみ開始されます。</td>
<td>通常の動作通知。アクションは必要ありません。<br>
システムの再起動後もこのエラーが解決しない場合は、すべての Windows 更新プログラムが完全にインストールされていることを確認します。</td>
</tr>
<tr>
<td>20</td>
<td>OOBE (Windows ようこそ) が完了するのを待つ必要があります。 エラー コード: <code>variable</code> .</td>
<td>内部エラー。</td>
<td>システムの再起動後もこのエラーが解決しない場合は、すべての Windows 更新プログラムが完全にインストールされていることを確認します。</td>
</tr>
<tr>
<td>25</td>
<td>Microsoft Defender for Endpoint service は、レジストリの正常性状態をリセットできなかった。 エラー コード: <code>variable</code> .</td>
<td>デバイスが正しくオンボードされませんでした。
ポータルに報告しますが、サービスが SCCM またはレジストリに登録されていない場合があります。</td>
<td>オンボーディング設定とスクリプトが適切に展開されていることを確認します。 構成パッケージを再展開してみてください。<br>
「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</td>
</tr>
<tr>
<td>26</td>
<td>Microsoft Defender for Endpoint service は、レジストリのオンボーディングの状態を設定できなかった。 エラー コード: <code>variable</code> .</td>
<td>デバイスが正しくオンボードされませんでした。<br>
ポータルに報告しますが、サービスが SCCM またはレジストリに登録されていない場合があります。</td>
<td>オンボーディング設定とスクリプトが適切に展開されていることを確認します。 構成パッケージを再展開してみてください。<br>
「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</td>
</tr>
<tr>
<td>27</td>
<td>Microsoft Defender for Endpoint Service は、Microsoft Defender ウイルス対策で SENSE 対応モードを有効にできなかった。 オンボーディング プロセスに失敗しました。 エラー コード: <code>variable</code> .</td>
<td>通常、別のリアルタイムマルウェア対策製品がデバイスで適切に実行され、デバイスが Defender for Endpoint に報告されている場合、Microsoft Defender ウイルス対策は特別なパッシブ状態になります。</td>
<td>オンボーディング設定とスクリプトが適切に展開されていることを確認します。 構成パッケージを再展開してみてください。<br>
「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。<br>
リアルタイムのマルウェア対策保護が正しく実行されていることを確認します。</td>
</tr>
<tr>
<td>28</td>
<td>Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed. エラー コード: <code>variable</code> .</td>
<td>Windows テレメトリ サービスでエラーが発生しました。</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">診断データ サービスが有効になっているか確認します</a>。<br>
オンボーディング設定とスクリプトが適切に展開されていることを確認します。 構成パッケージを再展開してみてください。<br>
「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</td>
</tr>
<tr>
<td>29</td>
<td>オフボード パラメーターの読み取りに失敗しました。 エラーの種類: %1、エラー コード: %2、説明: %3 </td>
<td>このイベントは、システムがオフボード パラメーター&#39;読み取りできない場合に発生します。</td>
<td>デバイスにインターネット アクセス権が設定されているのを確認し、オフボード プロセス全体を再度実行します。 オフボード パッケージの有効期限が切れていないか確認します。</td>
</tr>
<tr>
<td>30</td>
<td>Microsoft Defender for Endpoint Service は、Microsoft Defender ウイルス対策で SENSE 対応モードを無効にできなかった。 エラー コード: <code>variable</code> .</td>
<td>通常、別のリアルタイムマルウェア対策製品がデバイスで適切に実行され、デバイスが Defender for Endpoint に報告されている場合、Microsoft Defender ウイルス対策は特別なパッシブ状態になります。</td>
<td>オンボーディング設定とスクリプトが適切に展開されていることを確認します。 構成パッケージを再展開してみてください。<br>
「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください。</a><br>
リアルタイムのマルウェア対策保護が正しく実行されていることを確認します。</td>
</tr>
<tr>
<td>31</td>
<td>Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed. エラー コード: <code>variable</code> .</td>
<td>オンボード中に Windows テレメトリ サービスでエラーが発生しました。 オフボードプロセスは続行されます。</td>
<td><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Windows テレメトリ サービスのエラーを確認します</a>。</td>
</tr>
<tr>
<td>32</td>
<td>Microsoft Defender for Endpoint service は、オフボード プロセスの後に自身を停止する要求に失敗しました。 エラー コード: %1</td>
<td>オフボード中にエラーが発生しました。</td>
<td>デバイスを再起動します。</td>
</tr>
<tr>
<td>33</td>
<td>エンドポイント サービスの Microsoft Defender は、SENSE GUID の永続化に失敗しました。 エラー コード: <code>variable</code> .</td>
<td>一意の識別子を使用して、ポータルに報告する各デバイスを表します。<br>
識別子が保持されない場合、同じデバイスがポータルに 2 回表示される場合があります。</td>
<td>サービスがレジストリを更新できるデバイスのレジストリのアクセス許可を確認します。</td>
</tr>
<tr>
<td>34</td>
<td>Microsoft Defender for Endpoint Service は、接続されたユーザー エクスペリエンスとテレメトリ サービスへの依存関係として自分自身を追加できなかったので、オンボーディング プロセスが失敗しました。 エラー コード: <code>variable</code> .</td>
<td>Windows テレメトリ サービスでエラーが発生しました。</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">診断データ サービスが有効になっているか確認します</a>。<br>
オンボーディング設定とスクリプトが適切に展開されていることを確認します。 構成パッケージを再展開してみてください。<br>
「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</td>
</tr>
<tr>
<td>35</td>
<td>Microsoft Defender for Endpoint Service は、接続されたユーザー エクスペリエンスとテレメトリ サービスへの依存関係として削除に失敗しました。 エラー コード: <code>variable</code> .</td>
<td>オフボード中に Windows テレメトリ サービスでエラーが発生しました。 オフボードプロセスは続行されます。
</td>
<td>Windows 診断データ サービスのエラーを確認します。</td>
</tr>
<tr>
<td>36</td>
<td>Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded. 完了コード: <code>variable</code> .</td>
<td>Defender for Endpoint の接続ユーザー エクスペリエンスとテレメトリ サービスへの登録が正常に完了しました。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>37</td>
<td>Microsoft Defender for Endpoint A モジュールは、クォータを超えかねない状態です。 モジュール: %1、クォータ: {%2} {%3}、クォータ使用率の割合: %4。</td>
<td>デバイスは、現在の 24 時間ウィンドウの割り当てられたクォータをほとんど使用しています。 調整が必要です。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>38</td>
<td>ネットワーク接続は低として識別されます。 Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。 メーター接続: %2、インターネット利用可:%3、利用可能な無料ネットワーク:%4。</td>
<td>デバイスは、測定済み/有料ネットワークを使用し、サーバーへの接続頻度が低い。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>39</td>
<td>ネットワーク接続は通常と識別されます。 Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。 メーター接続: %2、インターネット利用可:%3、利用可能な無料ネットワーク:%4。</td>
<td>デバイスは、メーター接続または有料接続を使用していなく、通常どおりサーバーに連絡します。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>40</td>
<td>バッテリーの状態は低と識別されます。 Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。 バッテリーの状態: %2。</td>
<td>デバイスのバッテリー 残量が少なく、サーバーに接続する頻度が低い。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>41</td>
<td>バッテリーの状態は、通常の状態として識別されます。 Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。 バッテリーの状態: %2。</td>
<td>デバイスのバッテリー 残量が少なめで、通常どおりサーバーに連絡します。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>42</td>
<td>Microsoft Defender for Endpoint コンポーネントは、アクションの実行に失敗しました。 コンポーネント: %1、Action: %2、例外の種類: %3、例外メッセージ: %4</td>
<td>内部エラー。 サービスの開始に失敗しました。</td>
<td>このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
<td>43</td>
<td>Microsoft Defender for Endpoint コンポーネントは、アクションの実行に失敗しました。 コンポーネント: %1、Action: %2、例外の種類: %3、例外エラー: %4、例外メッセージ: %5</td>
<td>内部エラー。 サービスの開始に失敗しました。</td>
<td>このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
<td>44</td>
<td>Defender for Endpoint サービスのオフボーディングが完了しました。</td>
<td>サービスはオフボードされました。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>45</td>
<td>イベント トレース セッション [%1] の登録と開始に失敗しました。 エラー コード: %2</td>
<td>ETW セッションの作成時にサービスの起動時にエラーが発生しました。 これにより、サービスの起動エラーが発生しました。</td>
<td>このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
<td>46</td>
<td>リソース不足のため、イベント トレース セッション [%1] の登録と開始に失敗しました。 エラー コード: %2。 これは、アクティブなイベント トレース セッションが多すぎるためです。 サービスは 1 分で再試行します。</td>
<td>リソース不足のため、ETW セッションの作成中にサービスの起動時にエラーが発生しました。 サービスは開始され、実行中ですが、ETW セッションが開始されるまでセンサー イベントは報告できません。</td>
<td>通常の動作通知。アクションは必要ありません。 サービスは、1 分ごとにセッションを開始します。</td>
</tr>
<tr>
<td>47</td>
<td>イベント トレース セッションが正常に登録され、開始されました 。 以前に失敗した試行後に回復されました。</td>
<td>このイベントは、ETW セッションを正常に開始した後、前のイベントに従います。</td>
<td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
<td>48</td>
<td>イベント トレース セッション [%2] にプロバイダー [%1] を追加できなかった。 エラー コード: %3。 つまり、このプロバイダーからのイベントは報告されません。</td>
<td>ETW セッションにプロバイダーを追加できなかった。 その結果、プロバイダー イベントは報告されません。</td>
<td>エラー コードを確認します。 エラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
</tr>
<tr>
   <td>49</td>
   <td>無効なクラウド構成コマンドが受信され、無視されます。 バージョン: %1、状態: %2、エラー コード: %3、メッセージ: %4</td>
   <td>無視されたクラウド サービスから無効な構成ファイルを受け取った。</td>
   <td>このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>50</td>
   <td>新しいクラウド構成が正常に適用されました。 バージョン: %1。</td>
   <td>クラウド サービスから新しい構成を正常に適用しました。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>51</td>
   <td>新しいクラウド構成の適用に失敗しました。バージョン: %1。 最後の既知の良い構成であるバージョン %2 が正常に適用されました。</td>
   <td>クラウド サービスから悪い構成ファイルを受け取った。 最後に既知の良好な構成が正常に適用されました。</td>
   <td>このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>52</td>
   <td>新しいクラウド構成の適用に失敗しました。バージョン: %1。 また、前回の既知の良好な構成バージョン %2 の適用にも失敗しました。 既定の構成が正常に適用されました。</td>
   <td>クラウド サービスから悪い構成ファイルを受け取った。 前回の既知の良好な構成の適用に失敗し、既定の構成が適用されました。</td>
   <td>サービスは、5 分以内に新しい構成ファイルのダウンロードを試みます。 イベント が表示#50サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>53</td>
   <td>永続的な記憶域から読み込まれたクラウド構成のバージョン: %1。</td>
   <td>構成は、サービスの起動時に永続的な記憶域から読み込まれた。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>55</td>
   <td>Secure ETW 自動ロガーの作成に失敗しました。 エラー コード: %1</td>
   <td>セキュリティで保護された ETW ロガーの作成に失敗しました。</td>
   <td>デバイスを再起動します。 このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>56</td>
   <td>Secure ETW 自動ロガーの削除に失敗しました。 エラー コード: %1</td>
   <td>オフボーディング時にセキュリティで保護された ETW セッションを削除できなかった。</td>
   <td>サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>57</td>
   <td>トラブルシューティングの目的でコンピューターのスナップショットをキャプチャする。</td>
   <td>調査パッケージ (forensics パッケージとも呼ばれる) が収集されています。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>59</td>
   <td>開始コマンド: %1</td>
   <td>応答コマンドの実行を開始します。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>60</td>
   <td>コマンド %1 の実行に失敗しました。エラー: %2。</td>
   <td>応答コマンドの実行に失敗しました。</td>
   <td>このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>61</td>
   <td>データ収集コマンド パラメーターが無効です。SasUri: %1、compressionLevel: %2。</td>
   <td>データ収集コマンドの引数 (無効な引数) の読み取りまたは解析に失敗しました。</td>
   <td>このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>62</td>
   <td>接続ユーザー エクスペリエンスとテレメトリ サービスの開始に失敗しました。 エラー コード: %1</td>
   <td>接続されたユーザー エクスペリエンスとテレメトリ (diagtrack) サービスの開始に失敗しました。 Microsoft Defender for Endpoint テレメトリ以外は、このコンピューターから送信されません。</td>
   <td>イベント ログのトラブルシューティング のヒントを探します。Microsoft-Windows-UniversalTelemetryClient/Operational。</td>
</tr>
<tr>
   <td>63</td>
   <td>外部サービスの開始の種類を更新します。 名前: %1、実際の開始の種類: %2、予期される開始の種類: %3、終了コード: %4</td>
   <td>外部サービスの開始の種類を更新しました。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>64</td>
   <td>停止した外部サービスの開始。 名前: %1、終了コード: %2</td>
   <td>外部サービスの開始。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>65</td>
   <td>Microsoft セキュリティ イベント コンポーネント ミニフィルター ドライバーの読み込みに失敗しました。 エラー コード: %1</td>
   <td>ファイルシステムのミニフィルターMsSecFlt.sys読み込めない。</td>
   <td>デバイスを再起動します。 このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>66</td>
   <td>ポリシー更新プログラム: 待機時間モード - %1</td>
   <td>C&C 接続頻度ポリシーが更新されました。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>68</td>
   <td>サービスの開始の種類が予期しない。 サービス名: %1、実際の開始の種類: %2、予期される開始の種類: %3</td>
   <td>予期しない外部サービスの開始の種類。</td>
   <td>外部サービスの開始の種類を修正します。</td>
</tr>
<tr>
   <td>69</td>
   <td>サービスが停止します。 サービス名: %1</td>
   <td>外部サービスが停止します。</td>
   <td>外部サービスを開始します。</td>
</tr>
<tr>
   <td>70</td>
   <td>ポリシー更新: サンプル コレクションを許可する - %1</td>
   <td>サンプル コレクション ポリシーが更新されました。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>71</td>
   <td>コマンドの実行に成功しました: %1</td>
   <td>コマンドが正常に実行されました。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>72</td>
   <td>最初の完全なコンピューター プロファイル レポートの送信を試みました。 結果コード: %1</td>
   <td>情報提供のみ。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>73</td>
   <td>プラットフォームの開始センス: %1</td>
   <td>情報提供のみ。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>74</td>
   <td>レジストリ内のデバイス タグが長さの制限を超えています。 タグ名: %2。 長さの制限: %1。</td>
   <td>デバイス タグが長さの制限を超えています。</td>
   <td>短いデバイス タグを使用します。</td>
</tr>
<tr>
   <td>81</td>
   <td>エンドポイント ETW 自動ロガー用 Microsoft Defender の作成に失敗しました。 エラー コード: %1</td>
   <td>ETW セッションの作成に失敗しました。</td>
   <td>デバイスを再起動します。 このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>82</td>
   <td>エンドポイント ETW 自動ロガー用 Microsoft Defender の削除に失敗しました。 エラー コード: %1</td>
   <td>ETW セッションの削除に失敗しました。</td>
   <td>サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>84</td>
   <td>ウイルス対策Windows Defenderモードを設定します。 強制パッシブ モード: %1、結果コード: %2。</td>
   <td>Defender の実行モード (アクティブまたはパッシブ) を設定します。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>85</td>
   <td>Microsoft Defender for Endpoint 実行可能ファイルのトリガーに失敗しました。 エラー コード: %1</td>
   <td>SenseIR 実行可能ファイルの主演に失敗しました。</td>
   <td>デバイスを再起動します。 このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>86</td>
   <td>もう一度開始すると、起動する必要がある外部サービスが停止しました。 名前: %1、終了コード: %2</td>
   <td>外部サービスを再度開始します。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>87</td>
   <td>外部サービスを開始できません。 名前: %1</td>
   <td>外部サービスの開始に失敗しました。</td>
   <td>サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>88</td>
   <td>外部サービスの開始の種類を再度更新します。 名前: %1、実際の開始の種類: %2、予期される開始の種類: %3、終了コード: %4</td>
   <td>外部サービスの開始の種類を更新しました。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>89</td>
   <td>外部サービスの開始の種類を更新できません。 名前: %1、実際の開始の種類: %2、予期される開始の種類: %3</td>
   <td>外部サービスの開始の種類を更新できない。</td>
   <td>サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>90</td>
   <td>地域 %1 のクラウド サービスに接続するための System Guard ランタイム モニターの構成に失敗しました。 エラー コード: %2</td>
   <td>System Guard ランタイム モニターは、構成証明データをクラウド サービスに送信しない。</td>
   <td>登録パスのアクセス許可を確認します。"HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。 問題が見つからない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>91</td>
   <td>System Guard ランタイム モニター地域情報の削除に失敗しました。 エラー コード: %1</td>
   <td>System Guard ランタイム モニターは、構成証明データをクラウド サービスに送信しない。</td>
   <td>登録パスのアクセス許可を確認します。"HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。 問題が見つからない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>92</td>
   <td>データ クォータを超えたため、センサーのサイバー データ クォータの送信を停止します。 クォータ期間が過ぎると、送信が再開されます。 状態マスク: %1</td>
   <td>調整の制限を超える。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>93</td>
   <td>センサーのサイバー データの送信を再送信する。 状態マスク: %1</td>
   <td>サイバー データの送信を再開します。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>94</td>
   <td>Microsoft Defender for Endpoint 実行可能ファイルが開始されました</td>
   <td>SenseCE 実行可能ファイルが開始されました。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>95</td>
   <td>Microsoft Defender for Endpoint 実行可能ファイルが終了しました</td>
   <td>SenseCE 実行可能ファイルが終了しました。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>96</td>
   <td>Microsoft Defender for Endpoint Init が呼び出しました。 結果コード: %2</td>
   <td>SenseCE 実行可能ファイルは MCE 初期化と呼ばされています。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>97</td>
   <td>DLP シナリオのクラウドへの接続に関する問題がある</td>
   <td>DLP 分類フローに影響するネットワーク接続の問題があります。</td>
   <td>ネットワーク接続を確認します。</td>
</tr>
<tr>
   <td>98</td>
   <td>DLP シナリオのクラウドへの接続が復元されました</td>
   <td>ネットワークへの接続が復元され、DLP 分類フローを続行できます。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>99</td>
   <td>サーバーとの通信中に、センスで次のエラーが発生しました。(%1)。 結果: (%2)</td>
   <td>通信エラーが発生しました。</td>
   <td>詳細については、イベント ログで次のイベントを確認してください。</td>
</tr>
<tr>
   <td>100</td>
   <td>Microsoft Defender for Endpoint 実行可能ファイルの起動に失敗しました。 エラー コード: %1</td>
   <td>SenseCE 実行可能ファイルの起動に失敗しました。</td>
   <td>デバイスを再起動します。 このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
   <td>102</td>
   <td>Microsoft Defender for Endpoint Network Detection and Response 実行可能ファイルが開始されました</td>
   <td>SenseNdr 実行可能ファイルが開始されました。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
<tr>
   <td>103</td>
   <td>Microsoft Defender for Endpoint Network Detection and Response 実行可能ファイルが終了しました</td>
   <td>SenseNdr 実行可能ファイルが終了しました。</td>
   <td>通常の動作通知。アクションは必要ありません。</td>
</tr>
</tbody>
</table>

>Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>関連項目
- [Windows 10 デバイスのオンボード](configure-endpoints.md)
- [デバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)
- [Microsoft Defender for Endpoint のトラブルシューティング](troubleshoot-onboarding.md)

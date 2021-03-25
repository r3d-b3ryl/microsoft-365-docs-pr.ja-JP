---
title: イベント ビューアーを使用してイベントとエラーを確認する
description: Microsoft Defender for Endpoint サービスによって報告されたすべてのイベントの説明とトラブルシューティング手順 (必要な場合) を取得します。
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
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068580"
---
# <a name="review-events-and-errors-using-event-viewer"></a>イベント ビューアーを使用してイベントとエラーを確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- イベント ビューアー
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

イベントの ID は、個々のデバイスの [イベント ビューアー](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) で確認できます。

たとえば、[デバイス] リストにデバイスが表示されない場合は、デバイスでイベントの ID を探す必要があります。 次に、この表を使用して、さらにトラブルシューティングの手順を決定できます。

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
<th>アクション</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft Defender for Endpoint service が開始されました (バージョン <code>variable</code> )。</td>
<td>システムの起動、シャットダウン、およびオンボード中に発生します。</td>
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
<td>デバイスは、メーター接続または有料接続を使用していないので、通常どおりサーバーに連絡します。</td>
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
<td>Microsoft Defender for Endpoint WDATP コンポーネントは、アクションの実行に失敗しました。 コンポーネント: %1、Action: %2、例外の種類: %3、例外メッセージ: %4</td>
<td>内部エラー。 サービスの開始に失敗しました。</td>
<td>このエラーが解決しない場合は、サポートにお問い合わせください。</td>
</tr>
<tr>
<td>43</td>
<td>Microsoft Defender for Endpoint WDATP コンポーネントは、アクションの実行に失敗しました。 コンポーネント: %1、Action: %2、例外の種類: %3、例外エラー: %4、例外メッセージ: %5</td>
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
</tbody>
</table>

>Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>関連項目
- [オンボード Windows 10 デバイス](configure-endpoints.md)
- [デバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)
- [エンドポイントの Microsoft Defender のトラブルシューティング](troubleshoot-onboarding.md)

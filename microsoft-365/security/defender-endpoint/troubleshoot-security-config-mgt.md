---
title: Microsoft Defender for Endpointの Security Management に関連するオンボードの問題のトラブルシューティング
description: Microsoft Defender for Endpoint用の Security Management を使用してデバイスのオンボード中に発生する可能性がある問題のトラブルシューティングを行います。
keywords: オンボード、オンボードの問題、イベント ビューアー、データ収集とプレビュー ビルド、センサー データと診断のトラブルシューティング
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 0ceb24b5da0947dbb2b79ca7560ffbb46b701b38
ms.sourcegitcommit: 2aa5c026cc06ed39a9c1c2bcabd1f563bf5a1859
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2022
ms.locfileid: "66696274"
---
# <a name="troubleshoot-onboarding-issues-related-to-security-management-for-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointの Security Management に関連するオンボードの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft エンドポイント マネージャーを使用してデバイスのMicrosoft Defender for Endpointを管理する](/mem/intune/protect/mde-security-integration)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender for Endpoint用の Security Management は、microsoft エンドポイント マネージャーによって管理されていないデバイス (Microsoft Intuneまたは Microsoft Endpoint Configuration Manager) が、セキュリティ構成を受信するための機能です。エンドポイント マネージャーから直接Microsoft Defender for Endpointします。
Microsoft Defender for Endpoint用のセキュリティ管理の詳細については、「[Microsoft エンドポイント マネージャーを使用したデバイスでのMicrosoft Defender for Endpointの管理」を](/mem/intune/protect/mde-security-integration)参照してください。

Microsoft Defender for Endpointオンボード手順の Security Management については、「[セキュリティ構成管理Microsoft Defender for Endpoint」を](security-config-management.md)参照してください。

このエンドツーエンドのオンボードは、摩擦がないように設計されており、ユーザー入力は必要ありません。 ただし、オンボード中に問題が発生した場合は、Microsoft Defender for Endpoint プラットフォーム内でエラーを表示およびトラブルシューティングできます。

> [!NOTE]
> 新しいデバイスのオンボード フローに問題がある場合は、[Microsoft Defender for Endpointの前提条件](/mem/intune/protect/mde-security-integration#prerequisites)を確認し、オンボード手順に従っていることを確認します。

クライアント アナライザーの詳細については、「[Microsoft Defender for Endpoint Client Analyzer を使用したセンサーの正常性のトラブルシューティング](/microsoft-365/security/defender-endpoint/overview-client-analyzer)」を参照してください。

## <a name="registering-domain-joined-computers-with-azure-active-directory"></a>ドメインに参加しているコンピューターを Azure Active Directory に登録する

Azure Active Directory にデバイスを正常に登録するには、次のことを確認する必要があります。

- コンピューターはドメイン コントローラーで認証できます
- コンピューターは、組織のネットワーク内から次の Microsoft リソースにアクセスできます。
  - /windows/iot/iot-enterprise/commercialization/licensing
  - https://login.microsoftonline.com
  - https://device.login.microsoftonline.com
- Azure AD 接続は、コンピューター オブジェクトを同期するように構成されています。 既定では、コンピューター OU は Azure AD Connect 同期スコープ内にあります。 コンピューター オブジェクトが特定の組織単位 (OU) に属している場合は、Azure AD Connect で同期するように OU を構成します。 Azure AD Connect を使用してコンピューター オブジェクトを同期する方法の詳細については、「 [組織単位ベースのフィルター処理](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering#organizational-unitbased-filtering)」を参照してください。

> [!IMPORTANT]
> Azure AD connect では、R2 コンピューター オブジェクトWindows Server 2012同期されません。 Microsoft Defender for Endpoint用に Azure AD for Security Management に登録する必要がある場合は、同期スコープにそれらのコンピューター オブジェクトを含めるために Azure AD 接続同期規則をカスタマイズする必要があります。 [Azure Active Directory Connect でコンピューター参加規則を適用する手順に関するページを]()参照してください。

> [!NOTE]
> オンボード フローを正常に完了し、デバイスのオペレーティング システムに依存しない場合は、デバイスの初期状態に基づいて、デバイスの Azure Active Directory 状態を変更できます。
>
> <br>
>
>|デバイス状態の開始|新しいデバイスの状態|
>|---|---|
>|既に AADJ または|そのまま残る|
>|AADJ またはハイブリッド Azure Active Directory Join (一部の AZURE Active Directory Join (10000) + ドメインが参加していない|デバイスは、一部のデバイスに含まれます。|
>|AADJ または一時設定なし + ドメインに参加していません|デバイスは AADJ'd です|
>
> ここで、AADJ は Azure Active Directory Joined を表し、SECURITYJ は Hybrid Azure Active Directory Joined を表します。

## <a name="troubleshoot-errors-from-the-microsoft-defender-for-endpoint-portal"></a>Microsoft Defender for Endpoint ポータルからのエラーのトラブルシューティング

Microsoft Defender for Endpoint ポータルを使用して、セキュリティ管理者はMicrosoft Defender for Endpointオンボード用の Security Management のトラブルシューティングを行うことができます。

**構成管理** では、**MDE によるオンボード セキュリティ管理** ウィジェットが追加され、Microsoft Defender for Endpointマネージド デバイスの登録状態の内訳が表示されます。

Microsoft Defender for Endpointによって管理されているすべてのデバイスの一覧を表示するには、[**MDE によって管理されているすべてのデバイスを表示する**] を選択します。

一覧で、デバイスの登録状態が "成功" でない場合は、デバイスを選択してサイド パネルにトラブルシューティングの詳細を表示し、エラーの根本原因と対応するドキュメントを示します。


:::image type="content" source="./images/secconfig-mde-error.png" alt-text="デバイス インベントリ ページに適用されるフィルター条件" lightbox="./images/secconfig-mde-error.png":::

> [!NOTE] 
> セキュリティ管理機能を使用しようとして修正に取り組んでいるときに、サード パーティの MMM の正確な検出に影響を与える問題を認識しています。 

## <a name="run-microsoft-defender-for-endpoint-client-analyzer-on-windows"></a>Windows でクライアント アナライザー Microsoft Defender for Endpoint実行する

Microsoft Defender for Endpointオンボード フローの Security Management を完了できないエンドポイントでクライアント アナライザーを実行することを検討してください。 クライアント アナライザーの詳細については、「[Microsoft Defender for Endpoint Client Analyzer を使用したセンサーの正常性のトラブルシューティング](overview-client-analyzer.md)」を参照してください。

Client Analyzer 出力ファイル (MDE クライアント アナライザー Results.htm) は、次の主要なトラブルシューティング情報を提供できます。

- [**一般的** なデバイスの詳細] セクションで、デバイス OS が Microsoft Defender for Endpointオンボード フローの Security Management のスコープ内にあることを確認します
- デバイス **構成管理の詳細** で、デバイスが Azure Active Directory に正常に登録されたことを確認します

  :::image type="content" source="images/client-analyzer-results.png" alt-text="クライアント アナライザーの結果" lightbox="images/client-analyzer-results.png":::

レポートの **[詳細な結果]** セクションでは、クライアント アナライザーも実用的なガイダンスを提供します。

> [!TIP]
> レポートの [詳細な結果] セクションに "エラー" が含まれていないことを確認し、すべての "警告" メッセージを確認してください。

たとえば、Security Management オンボード フローの一環として、Microsoft Defender for Endpoint テナントの Azure Active Directory テナント ID が、レポートの **[デバイス構成管理の詳細]** セクションに表示される SCP テナント ID と一致するようにする必要があります。 関連する場合は、レポート出力でこの検証を実行することをお勧めします。

:::image type="content" source="images/detailed-results.png" alt-text="詳細な結果を表示するページ" lightbox="images/detailed-results.png"

## <a name="general-troubleshooting"></a>一般的なトラブルシューティング

AAD または MEM でオンボードされたデバイスを識別できず、登録中にエラーが発生しなかった場合は、レジストリ キー `Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SenseCM\\EnrollmentStatus` を確認すると、追加のトラブルシューティング情報が提供される可能性があります。

:::image type="content" source="images/enrollment-status.png" alt-text="登録状態を表示するページ" lightbox="images/enrollment-status.png":::

次の表に、エラーに対処するために試行または確認する内容に関するエラーと指示の一覧を示します。 エラーの一覧は完全ではなく、過去に顧客が発生した一般的なエラーまたは一般的なエラーに基づいていることに注意してください。

|エラー コード|登録状態|管理者のアクション|
|---|---|---|
|`5-7`, `9`, `11-12`, `26-33`|一般的なエラー|デバイスが正常にMicrosoft Defender for Endpointにオンボードされました。 ただし、セキュリティ構成管理フローでエラーが発生しました。 これは、デバイスが[Microsoft Defender for Endpoint管理チャネルの前提条件を](security-config-management.md)満たしていない可能性があります。 デバイスで [クライアント アナライザー](https://aka.ms/BetaMDEAnalyzer) を実行すると、問題の根本原因を特定するのに役立ちます。 問題が解決しない場合は、サポートにお問い合わせください。|
| `8`, `44` | Microsoft エンドポイント マネージャー構成の問題 | デバイスが正常にMicrosoft Defender for Endpointにオンボードされました。 ただし、Microsoft エンドポイント マネージャーは、Microsoft Defender for Endpointセキュリティ構成を許可するように管理 センターを介して構成されていません。 [Microsoft エンドポイント マネージャー テナントが構成され、機能がオン](/mem/intune/protect/mde-security-integration#configure-your-tenant-to-support-microsoft-defender-for-endpoint-security-configuration-management)になっていることを確認します。|
|`13-14`,`20`,`24`,`25`|接続の問題|デバイスが正常にMicrosoft Defender for Endpointにオンボードされました。 ただし、接続の問題が原因である可能性があるセキュリティ構成管理フローにエラーが発生しました。 [Azure Active Directory エンドポイントと Microsoft エンドポイント マネージャー エンドポイント](security-config-management.md#connectivity-requirements)がファイアウォールで開かれていることを確認します。|
|`10`,`42`|一般的なハイブリッド結合エラー|デバイスが正常にMicrosoft Defender for Endpointにオンボードされました。 ただし、セキュリティ構成管理フローにエラーが発生し、OS でハイブリッド参加を実行できませんでした。 OS レベル [のハイブリッド参加エラーのトラブルシューティングには、ハイブリッド Azure Active Directory 参加済みデバイス](/azure/active-directory/devices/troubleshoot-hybrid-join-windows-current) のトラブルシューティングを使用します。|
|`15`|テナントの不一致|デバイスが正常にMicrosoft Defender for Endpointにオンボードされました。 ただし、Microsoft Defender for Endpoint テナント ID が Azure Active Directory テナント ID と一致しないため、セキュリティ構成管理フローでエラーが発生しました。 Defender for Endpoint テナントの Azure Active Directory テナント ID が、ドメインの SCP エントリのテナント ID と一致していることを確認します。 詳細については、「[Microsoft Defender for Endpointの Security Management に関連するオンボードの問題のトラブルシューティング」を参照](troubleshoot-security-config-mgt.md)してください。|
|`16`,`17`|ハイブリッド エラー - サービス接続ポイント|デバイスが正常にMicrosoft Defender for Endpointにオンボードされました。 ただし、サービス接続ポイント (SCP) レコードが正しく構成されておらず、デバイスを Azure AD に参加させることができませんでした。 これは、SCP が Enterprise DRS に参加するように構成されていることが原因である可能性があります。 SCP レコードが AAD を指し示し、SCP が次のベスト プラクティスに従って構成されていることを確認します。 詳細については、「 [サービス接続ポイントの構成」を](/azure/active-directory/devices/hybrid-azuread-join-manual#configure-a-service-connection-point)参照してください。|
|`18`|証明書エラー|デバイスが正常にMicrosoft Defender for Endpointにオンボードされました。 ただし、デバイス証明書エラーが原因で、セキュリティ構成管理フローにエラーが発生しました。 デバイス証明書は別のテナントに属しています。 [信頼された証明書プロファイル](/mem/intune/protect/certificates-trusted-root#create-trusted-certificate-profiles)を作成するときにベスト プラクティスに従っていることを確認します。|
|`36` , `37`| AAD Connect の構成ミス |デバイスが正常にMicrosoft Defender for Endpointにオンボードされました。 ただし、AAD Connect の構成ミスにより、セキュリティ構成管理フローにエラーが発生しました。 デバイスが AAD に登録できない原因を特定するには、 [デバイス登録のトラブルシューティング ツール](/samples/azure-samples/dsregtool/dsregtool)を実行することを検討してください。 Windows Server 2012 R2 の場合は、[専用のトラブルシューティング手順を実行します](/azure/active-directory/devices/troubleshoot-hybrid-join-windows-legacy)。  |
|`38`,`41`|DNS エラー|デバイスが正常にMicrosoft Defender for Endpointにオンボードされました。 ただし、DNS エラーが原因で、セキュリティ構成管理フローにエラーが発生しました。 デバイスのインターネット接続または DNS 設定を確認します。 無効な DNS 設定がワークステーション側にある可能性があります。 Active Directory では、ドメイン DNS を使用して適切に動作する必要があります (ルーターのアドレスは使用しません)。 詳細については、「[Microsoft Defender for Endpointの Security Management に関連するオンボードの問題のトラブルシューティング」を](troubleshoot-security-config-mgt.md)参照してください。|
|`40`|クロック同期の問題|デバイスが正常にMicrosoft Defender for Endpointにオンボードされました。 ただし、セキュリティ構成管理フローでエラーが発生しました。 クロックが正しく設定され、エラーが発生したデバイスで同期されていることを確認します。|
|`43`|MDE と ConfigMgr|デバイスは、Configuration ManagerとMicrosoft Defender for Endpointを使用して管理されます。 両方のチャネルでポリシーを制御すると、競合や望ましくない結果が発生する可能性があります。 これを回避するには、エンドポイント セキュリティ ポリシーを 1 つのコントロール プレーンに分離する必要があります。 |

## <a name="azure-active-directory-runtime-troubleshooting"></a>Azure Active Directory ランタイムのトラブルシューティング

Azure Active Directory ランタイム (AADRT) のトラブルシューティングを行う主なメカニズムは、デバッグ トレースを収集することです。 Windows 上の Azure Active Directory ランタイムでは、 **ID bd67e65c-9cc2-51d8-7399-0bb9899e75c1 の ETW プロバイダー** が使用されます。 ETW トレースは、障害の再現と共にキャプチャする必要があります (たとえば、結合エラーが発生した場合は、AADRT API への呼び出しをカバーする期間、結合を実行するためにトレースを有効にする必要があります)。

AADRT ログの一般的なエラーとその読み方については、以下を参照してください。

:::image type="content" source="images/event-properties.png" alt-text="イベントのプロパティ ページ" lightbox="images/event-properties.png":::

メッセージの情報から、ほとんどの場合、発生したエラー、Win32 API によってエラーが返された内容 (該当する場合)、使用された URL (該当する場合)、AAD ランタイム API エラーが発生した内容を把握できます。

## <a name="instructions-for-applying-computer-join-rule-in-aad-connect"></a>AAD Connect でコンピューター参加規則を適用する手順

Windows Server 2012 R2 ドメインに参加しているコンピューター上のMicrosoft Defender for Endpoint用の Security Management では、Azure AD Connect 同期規則 "In from AD-Computer Join" の更新が必要です。 これは、元の "In from AD - Computer Join" ルールを無効にするルールを複製および変更することで実現できます。 既定では、Azure AD Connect では、組み込みのルールを変更するためのこのエクスペリエンスが提供されます。

> [!NOTE]
>これらの変更は、AAD Connect が実行されているサーバーに適用する必要があります。 AAD Connect のインスタンスが複数デプロイされている場合は、これらの変更をすべてのインスタンスに適用する必要があります。

1. スタート メニューから同期規則エディター アプリケーションを開きます。 ルールの一覧で、 **AD からコンピューターへの参加** という名前のルールを見つけます。 **このルールの [優先順位] 列の値を書き留めておきます。**

   :::image type="content" source="images/57ea94e2913562abaf93749d306dd6cf.png" alt-text="同期規則エディター" lightbox="images/57ea94e2913562abaf93749d306dd6cf.png":::

2. **[In from AD – Computer Join**] ルールが強調表示された状態で、[**編集]** を選択します。 [ **予約ルールの確認の編集** ] ダイアログ ボックスで、[ **はい**] を選択します。

   :::image type="content" source="images/8854440d6180a5580efda24110551c68.png" alt-text="予約ルールの編集の確認ページ" lightbox="images/8854440d6180a5580efda24110551c68.png":::

3. **[受信同期規則の編集]** ウィンドウが表示されます。 ルールの説明を更新して、Windows Server 2012R2 がこの規則を使用して同期されることに注意してください。 [優先順位] の値を除き、他のすべてのオプションは変更しません。 [優先順位] に、元のルールの値より大きい値を入力します (ルールの一覧に示すように)。

   :::image type="content" source="images/ee0f29162bc3f2fbe666c22f14614c45.png" alt-text="値を入力する受信同期規則の編集ページ" lightbox="images/ee0f29162bc3f2fbe666c22f14614c45.png":::

4. **[次へ]** を 3 回選択します。 これにより、ルールの [変換] セクションに移動します。 ルールの [スコープ フィルター] セクションと [結合ルール] セクションは変更しないでください。 [変換] セクションが表示されます。

   :::image type="content" source="images/296f2c2a705e41233631c3784373bc23.png" alt-text="受信同期規則" lightbox="images/296f2c2a705e41233631c3784373bc23.png":::

5. 変換の一覧の一番下までスクロールします。 **cloudFiltered** 属性の変換を見つけます。 **[ソース**] 列のテキスト ボックスで、すべてのテキスト (Control-A) を選択して削除します。 テキスト ボックスは空にする必要があります。

6. 新しいルールの内容をテキスト ボックスに貼り付けます。

    ```command
    IIF(
      IsNullOrEmpty([userCertificate])
      ||
      (
        (InStr(UCase([operatingSystem]),"WINDOWS") > 0)
        &&
        (Left([operatingSystemVersion],2) = "6.")
        &&
        (Left([operatingSystemVersion],3) <> "6.3")
      )
      ||
      (
        (Left([operatingSystemVersion],3) = "6.3")
        &&
        (InStr(UCase([operatingSystem]),"WINDOWS") > 0)
        &&
        With(
          $validCerts,
          Where(
            $c,
            [userCertificate],
            IsCert($c) && CertNotAfter($c) > Now() && RegexIsMatch(CertSubject($c), "CN=[{]*" & StringFromGuid([objectGUID]) & "[}]*", "IgnoreCase")),
          Count($validCerts) = 0)
      ),
      True,
      NULL
    )
    ```

7. [ **保存] を** 選択して、新しいルールを保存します。

> [!NOTE]
> この規則の変更が実行されると、Active Directory の完全な同期が必要になります。 大規模な環境の場合は、オンプレミスの Active Directory の静かな期間に、この規則の変更と完全同期をスケジュールすることをお勧めします。

## <a name="related-topic"></a>関連トピック

- [Microsoft エンドポイント マネージャーを使用してデバイスのMicrosoft Defender for Endpointを管理する](/mem/intune/protect/mde-security-integration)

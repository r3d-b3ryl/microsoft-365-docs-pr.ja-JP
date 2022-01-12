---
title: Microsoft Defender for Endpoint のセキュリティ管理に関連するオンボーディングの問題のトラブルシューティング
description: Microsoft Defender for Endpoint のセキュリティ管理を使用してデバイスのオンボーディング中に発生する可能性のある問題のトラブルシューティングを行います。
keywords: オンボーディング、オンボーディングの問題、イベント ビューアー、データ収集とプレビュー ビルド、センサー データ、診断のトラブルシューティング
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
ms.openlocfilehash: 9bff729d81a3db568560730d71ecd379fc60d5ce
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61867811"
---
# <a name="troubleshoot-onboarding-issues-related-to-security-management-for-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint のセキュリティ管理に関連するオンボーディングの問題のトラブルシューティング 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint on devices on devices with Microsoft エンドポイント マネージャー](/mem/intune/protect/mde-security-integration)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender for Endpoint のセキュリティ管理は、ユーザーまたはユーザーが管理していないデバイスMicrosoft エンドポイント マネージャー機能Microsoft IntuneですMicrosoft Endpoint Configuration Managerをクリックして、Microsoft Defender for Endpoint のセキュリティ構成を直接クライアントから受信エンドポイント マネージャー。
Microsoft Defender for Endpoint のセキュリティ管理の詳細については、「Manage Microsoft Defender for Endpoint on devices on devices with Microsoft エンドポイント マネージャー」 を[参照してください](/mem/intune/protect/mde-security-integration)。

Microsoft Defender for Endpoint オンボーディング手順のセキュリティ管理については[、「Microsoft Defender for Endpoint Security Configuration Management」を参照してください](security-config-management.md)。

このエンドツーエンドのオンボーディングは、フリクションレスに設計され、ユーザー入力を必要とします。 ただし、オンボーディング中に問題が発生した場合は、Microsoft Defender for Endpoint プラットフォーム内のエラーを表示およびトラブルシューティングできます。

> [!NOTE]
> 新しいデバイスのオンボーディング フローに問題がある場合は [、Microsoft Defender for Endpoint](/mem/intune/protect/mde-security-integration#prerequisites) の前提条件を確認し、オンボーディング手順に従ってください。

クライアント アナライザーの詳細については、「Microsoft Defender for Endpoint Client Analyzer を使用したセンサーの正常性のトラブルシューティング [」を参照してください](/microsoft-365/security/defender-endpoint/overview-client-analyzer)。

## <a name="registering-domain-joined-computers-with-azure-active-directory"></a>ドメインに参加しているコンピューターをドメインに登録Azure Active Directory
デバイスをデバイスに正常Azure Active Directoryするには、次の情報を確認する必要があります。

- コンピューターはドメイン コントローラーで認証できます 
- コンピューターは、組織のネットワーク内から次の Microsoft リソースにアクセスできます。
  - https://enterpriseregistration.windows.net
  - https://login.microsoftonline.com
  - https://device.login.microsoftonline.com
- Azure ADは、コンピューター オブジェクトを同期するように構成されています。 既定では、コンピューターの US は同期スコープAzure AD接続できません。 コンピューター オブジェクトが特定の組織単位 (OUs) に属している場合は、その組織単位で同期Azure AD Connect。 コンピューター オブジェクトを使用してコンピューター オブジェクトを同期する方法の詳細については、「組織単位Azure AD Connectフィルター」[を参照してください](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering#organizational-unitbased-filtering)。

> [!IMPORTANT]
> Azure ADは R2 コンピューター オブジェクトWindows Server 2012同期しません。 Microsoft Defender for Endpoint のセキュリティ管理用 Azure AD に登録する必要がある場合は、Azure AD 接続同期ルールをカスタマイズして、それらのコンピューター オブジェクトを同期スコープに含める必要があります。 「[コンピューター参加ルールを適用する手順」を参照Azure Active Directory Connect。]()

> [!NOTE]
> オンボード フローを正常に完了し、デバイスのオペレーティング システムとは別に、デバイスの Azure Active Directory 状態は、デバイスの初期状態に基づいて変更できます。<br>
>
> |      デバイスの状態の開始     |      新しいデバイスの状態     |
> |---|---|
> |     既に AADJ または HAADJ    |     そのまま残る    |
> |     AADJ またはハイブリッド Azure Active Directory参加 (HAADJ) + ドメインが参加していない    |     デバイスは HAADJ'd です    |
> |     AADJ または HAADJ ではない + ドメインに参加していない    |     デバイスは AADJ'd です    |
>
> ここで、AADJ は joined のAzure Active Directory HAADJ は、Joined のハイブリッド Azure Active Directoryします。

## <a name="troubleshoot-errors-from-the-microsoft-defender-for-endpoint-portal"></a>Microsoft Defender for Endpoint ポータルからのエラーのトラブルシューティング


Microsoft Defender for Endpoint ポータルを通じて、セキュリティ管理者は Microsoft Defender for Endpoint オンボーディングのセキュリティ管理をトラブルシューティングできます。 


Endpoints **> デバイス インベントリでは**、[ **管理** によって管理] 列が追加され、管理チャネル (MEM など) によってフィルター処理されます。


:::image type="content" alt-text="デバイス インベントリ ページのイメージ" source="./images/device-inventory-mde-error.png":::

Microsoft Defender for Endpoint オンボーディング プロセスのセキュリティ管理に失敗したすべてのデバイスの一覧を表示するには **、MDE-Error** でテーブルをフィルター処理します。

一覧で、特定のデバイスを選択して、サイド パネルにトラブルシューティングの詳細を表示し、エラーの根本原因と対応するドキュメントを示します。


:::image type="content" alt-text="フィルター処理されたデバイス インベントリ ページのイメージ" source="./images/secconfig-mde-error.png":::


## <a name="run-microsoft-defender-for-endpoint-client-analyzer-on-windows"></a>Microsoft Defender for Endpoint Client Analyzer をコンピューターで実行Windows 

Microsoft Defender for Endpoint オンボーディング フローのセキュリティ管理を完了できなかったエンドポイントでクライアント アナライザーを実行する方法を検討してください。 クライアント アナライザーの詳細については、「Microsoft Defender for Endpoint Client Analyzer を使用したセンサーの正常性のトラブルシューティング [」を参照してください](overview-client-analyzer.md)。

クライアント アナライザー出力ファイル (MDE クライアント アナライザー Results.htm) は、次の重要なトラブルシューティング情報を提供できます。

- [全般デバイスの詳細] セクションで、デバイス OS が Microsoft Defender for Endpoint オンボーディング フローのセキュリティ管理のスコープ **内にあるか確認** します。
- [デバイス構成管理の詳細] で、デバイスがAzure Active Directoryに登録 **されたことを確認します。**

    ![クライアント アナライザーの結果のイメージ](images/client-analyzer-results.png)

レポートの **[詳細な結果** ] セクションでは、クライアント アナライザーでも、操作可能なガイダンスを提供します。

> [!TIP]
> レポートの [詳細な結果] セクションに "エラー" が含めず、すべての "警告" メッセージを確認してください。

たとえば、セキュリティ管理オンボーディング フローの一部として、Microsoft Defender for Endpoint Tenant の Azure Active Directory テナント ID が、レポートの [デバイス構成管理の詳細]セクションに表示される SCP テナント ID と一致する必要があります。 関連する場合は、レポート出力でこの検証を実行することをお勧めします。

![詳細な結果の画像](images/detailed-results.png)

## <a name="general-troubleshooting"></a>一般的なトラブルシューティング

AAD または MEM でオンボード デバイスを識別できない場合に、登録中にエラーが表示されない場合は、レジストリ キーを確認すると、追加のトラブルシューティング情報を `Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SenseCM\\EnrollmentStatus` 提供できます。  

:::image type="content" alt-text="登録状態のイメージ。" source="images/enrollment-status.png":::

次の表に、エラーに対処するために何を試す/チェックする方法に関するエラーと指示を示します。 エラーの一覧は完全ではなく、過去に顧客が発生した一般的なエラーまたは一般的なエラーに基づく点に注意してください。

| エラー コード                    | 登録の状態                     | 管理者の操作                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-------------------------------|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ``5-9``,``11-12``, ``26-33``  |一般的なエラー                          |デバイスが正常に Microsoft Defender for Endpoint にオンボードされました。 ただし、セキュリティ構成管理フローにエラーが発生しました。 これは、デバイスが Microsoft Defender for Endpoint 管理チャネルの前提条件を満 [たしていない可能性があります](security-config-management.md)。 デバイスで [クライアント アナライザー](https://aka.ms/BetaMDEAnalyzer) を実行すると、問題の根本原因を特定できます。 それでも問題が生じなかった場合は、サポートにお問い合わせください。   |
| ``13-14``,``20``,``24``,``25``|接続の問題                     |デバイスが正常に Microsoft Defender for Endpoint にオンボードされました。 ただし、セキュリティ構成管理フローにエラーが発生し、接続の問題が原因である可能性があります。 ファイアウォールで[Azure Active Directory Microsoft エンドポイント マネージャーエンドポイント](security-config-management.md#connectivity-requirements)が開いているか確認します。                                                                                       |
| ``10``,``42``                 |一般的なハイブリッド参加の失敗            |デバイスが正常に Microsoft Defender for Endpoint にオンボードされました。 ただし、セキュリティ構成管理フローにエラーが発生し、OS がハイブリッド参加を実行できなかった。 OS[レベルのハイブリッドAzure Active Directory失敗の](/azure/active-directory/devices/troubleshoot-hybrid-join-windows-current)トラブルシューティングには、ハイブリッド デバイスに参加しているデバイスのトラブルシューティングを使用します。                                                                                                                               |
| ``15``                        |テナントの不一致                        |デバイスが正常に Microsoft Defender for Endpoint にオンボードされました。 ただし、Microsoft Defender for Endpoint テナント ID がテナント ID と一致しないので、セキュリティ構成管理フローにAzure Active Directoryでした。 Defender for Endpoint テナントAzure Active Directoryのテナント ID が、ドメインの SCP エントリのテナント ID と一致する必要があります。 詳細については、「Microsoft Defender for Endpoint のセキュリティ管理に関連するオンボードの問題 [のトラブルシューティング」を参照してください](troubleshoot-security-config-mgt.md)。|
| ``16``,``17``                 |ハイブリッド エラー - サービス接続ポイント|デバイスが正常に Microsoft Defender for Endpoint にオンボードされました。 ただし、サービス接続ポイント (SCP) レコードが正しく構成されていないので、デバイスをデバイスに参加Azure AD。 これは、SCP が DRS に参加するように構成Enterpriseがあります。 ベスト プラクティスに従って SCP レコードAAD SCP が構成されていることを確認します。 詳細については、「サービス接続ポイント [の構成」を参照してください](/azure/active-directory/devices/hybrid-azuread-join-manual#configure-a-service-connection-point)。                                                      |
| ``18``                        |証明書エラー                      |デバイスが正常に Microsoft Defender for Endpoint にオンボードされました。 ただし、デバイス証明書エラーが原因でセキュリティ構成管理フローにエラーが発生しました。 デバイス証明書は、別のテナントに属します。 信頼できる証明書プロファイルを作成するときにベスト プラクティスが実行 [されるのを確認します](/mem/intune/protect/certificates-trusted-root#create-trusted-certificate-profiles)。                                                                                                    |
| ``36``                        |LDAP API エラー                         |デバイスが正常に Microsoft Defender for Endpoint にオンボードされました。 ただし、セキュリティ構成管理フローにエラーが発生しました。 ネットワーク トポロジを確認し、ハイブリッド参加要求を完了するために LDAP API が使用できる必要があります。     |
| ``37``                        |オンプレミス同期の問題                  |デバイスが正常に Microsoft Defender for Endpoint にオンボードされました。 ただし、セキュリティ構成管理フローにエラーが発生しました。 後でもう一度お試しください。 それでも問題が解決しない場合は、「オブジェクト同期と同期[のトラブルシューティング」をAzure AD Connectしてください](/azure/active-directory/hybrid/tshoot-connect-objectsync)。|
| ``38``,``41``                 |DNS エラー                              |デバイスが正常に Microsoft Defender for Endpoint にオンボードされました。 ただし、DNS エラーが原因でセキュリティ構成管理フローにエラーが発生しました。 デバイスのインターネット接続や DNS 設定を確認します。 無効な DNS 設定がワークステーション側にある可能性があります。 Active Directory では、ドメイン DNS を使用して (ルーターのアドレスではなく) 正しく動作する必要があります。 詳細については、「Security Management for Microsoft Defender for Endpoint」に関連するオンボードの問題 [のトラブルシューティングを参照してください](troubleshoot-security-config-mgt.md)。             |
| ``40``                        |クロック同期の問題                       |デバイスが正常に Microsoft Defender for Endpoint にオンボードされました。 ただし、セキュリティ構成管理フローにエラーが発生しました。 クロックが正しく設定され、エラーが発生したデバイスで同期されていることを確認します。    |

## <a name="azure-active-directory-runtime-troubleshooting"></a>Azure Active Directoryランタイムのトラブルシューティング

### <a name="azure-active-directory-runtime"></a>Azure Active Directoryランタイム  

ランタイム (AADRT) のAzure Active Directoryする主なメカニズムは、デバッグ トレースを収集します。 Azure Active Directory ランタイム on Windows は **、ID bd67e65c-9cc2-51d8-7399-0bb9899e75c1** を持つ ETW プロバイダーを使用します。 ETW トレースは、エラーの再現と一緒にキャプチャする必要があります (たとえば、結合エラーが発生した場合は、参加を実行するために AADRT API の呼び出しをカバーする期間、トレースを有効にする必要があります)。  

AADRT ログの一般的なエラーと読み方については、以下を参照してください。

![イベント プロパティのイメージ](images/event-properties.png)

メッセージの情報から、ほとんどの場合、発生したエラー、エラーが返された Win32 API 、使用された URL (該当する場合)、および発生した AAD ランタイム API エラーを理解できます。 
  
 

## <a name="instructions-for-applying-computer-join-rule-in-aad-connect"></a>コンピューターの参加ルールをコンピューターに適用するAAD Connect 

Windows Server 2012 R2 ドメインに参加しているコンピューター上の Microsoft Defender for Endpoint のセキュリティ管理では、Azure AD Connect 同期ルール "in from AD-Computer Join" への更新が必要です。 これは、ルールを複製して変更することで実現できます。これにより、元の "In from AD - Computer Join" ルールが無効にされます。 Azure AD Connect既定では、組み込みのルールを変更する場合にこのエクスペリエンスが提供されます。

> [!NOTE]
>これらの変更は、サーバーが実行されているサーバー AAD Connect必要があります。 複数のインスタンスが展開されているAAD Connect、これらの変更をすべてのインスタンスに適用する必要があります。

1. スタート メニューから同期ルール エディター アプリケーションを開きます。 ルールの一覧で、[コンピューターの参加] の **[AD] という名前のルールを探します**。 **このルールの [優先順位] 列の値に注意してください。** 

    ![同期ルール エディターのイメージ](images/57ea94e2913562abaf93749d306dd6cf.png)

2. In from **AD – Computer Join** ルールが強調表示されている場合は、[編集] を **選択します**。 [予約ルール **の確認の編集] ダイアログ ボックスで** 、[はい] を **選択します**。 

   ![予約済みルールの編集確認のイメージ](images/8854440d6180a5580efda24110551c68.png)

3. [ **受信同期ルールの編集] ウィンドウ** が表示されます。 このルールを使用して、サーバー 2012R2 Windows同期される点に注意するルールの説明を更新します。 優先順位の値を除き、他のすべてのオプションは変更しないでください。 元のルールの値よりも高い優先順位の値を入力します (ルール一覧に表示されます)。  

   ![確認の画像](images/ee0f29162bc3f2fbe666c22f14614c45.png)

4. [次 **へ] を 3** 回選択します。 これにより、ルールの [変換] セクションに移動します。 ルールの 'スコープ フィルター' セクションと 'Join rules' セクションに変更を加えな [変換] セクションが表示されます。

    ![受信同期ホーンルールのイメージ](images/296f2c2a705e41233631c3784373bc23.png)

5. 変換の一覧の一番下までスクロールします。 **cloudFiltered 属性の変換を検索** します。 [ソース] 列の **テキスト ボックス** で、すべてのテキスト (Control-A) を選択して削除します。 これで、テキスト ボックスは空になります。 

6. 新しいルールのコンテンツをテキスト ボックスに貼り付けます。 


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

7.  [保存 **] を** 選択して新しいルールを保存します。

> [!NOTE]
> このルールの変更が実行された後、Active Directory の完全同期が必要になります。 大規模な環境では、オンプレミスの Active Directory の静かな期間中に、このルールの変更と完全同期をスケジュールする必要があります。

## <a name="related-topic"></a>関連トピック
- [Microsoft Defender for Endpoint on devices on devices with Microsoft エンドポイント マネージャー](/mem/intune/protect/mde-security-integration)

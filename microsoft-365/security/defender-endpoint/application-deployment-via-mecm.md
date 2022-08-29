---
title: Microsoft Monitoring Agent から統合ソリューションへのサーバーの移行
description: この記事では、Microsoft Monitoring Agent から新しい統合ソリューションに下位レベルのサーバーを段階的に移行する方法について説明します。
keywords: 移行サーバー, server, 2012r2, 2016, サーバー移行オンボード Microsoft Defender for Endpoint サーバー, MECM, Microsoft Monitoring Agent, MMA, ダウンレベル サーバー, 統合ソリューション, UA
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: alekyaj
ms.author: macapara
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 67d1f15ef79f932ad8515d8c8f6b5339845eb4f4
ms.sourcegitcommit: ab32c6e19af08837aaa84a058653c3a209d366ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2022
ms.locfileid: "67444941"
---
# <a name="migrating-servers-from-microsoft-monitoring-agent-to-the-unified-solution"></a>Microsoft Monitoring Agent から統合ソリューションへのサーバーの移行

**適用対象:**

- Windows Server 2012 R2
- Windows Server 2016

この記事では、Microsoft Monitoring Agent (MMA) から統合ソリューションに下位レベルのサーバーを移行する方法について説明します。

## <a name="prerequisites"></a>前提条件

- 2207 より前の Microsoft Endpoint Configuration Manager (MECM)。
- Microsoft Monitoring Agent にオンボードされた環境内の下位レベルの OS デバイス。 確認するには、タスク マネージャーで実行されていることを `MsSenseS.exe` 確認します。
- MMA エージェントの存在。 正しいワークスペース ID が コントロール パネル> Microsoft Monitoring Agent に存在するかどうかを確認することで確認できます。
- デバイスがオンボードされたアクティブなMicrosoft 365 Defender ポータル。
- WINDOWS SERVER 2012 R2 や MMA エージェントを使用したWindows Server 2016などの下位レベルのサーバーを含む **デバイス コレクション** は、MECM インスタンスに設定されます。

一覧表示されている前提条件のインストールの詳細については、 [関連トピック](#related-topics) のセクションを参照してください。

## <a name="gather-required-files"></a>必要なファイルを収集する

統合ソリューション パッケージ、オンボード スクリプト、移行スクリプトを、MECM を使用して他のアプリをデプロイするのと同じコンテンツ ソースにコピーします。

1. オンボード スクリプトと統合ソリューションを[Microsoft 365 Defender設定ページ](https://sip.security.microsoft.com/preferences2/onboarding)からダウンロードします。
   :::image type="content" source="images/onboarding-script.png" alt-text="オンボード スクリプトと統合ソリューションのダウンロードのスクリーンショット" lightbox="images/onboarding-script.png":::
   > [!Note]
   > .cmd ファイルを取得するには、Deployment メソッドのドロップダウンからグループ ポリシーを選択する必要があります。
2. ドキュメントから移行スクリプトをダウンロードします。[前の MMA ベースのMicrosoft Defender for Endpoint ソリューションのサーバー移行シナリオ](server-migration.md)。 このスクリプトは GitHub: [GitHub - microsoft/mdefordownlevelserver でも確認](https://github.com/microsoft/mdefordownlevelserver)できます。
3. MECM によってソフトウェア ソースとして使用される共有フォルダーに 3 つのファイルをすべて保存します。

   :::image type="content" source="images/ua-migration.png" alt-text="MECM によって共有フォルダーを保存するスクリーンショット。":::

## <a name="create-the-package-as-an-application"></a>アプリケーションとしてパッケージを作成する

1. MECM コンソールで、 **ソフトウェア ライブラリ>アプリケーション>アプリケーションの作成** の手順に従います。
2. [ **手動でアプリケーション情報を指定する] を選択します**。
   :::image type="content" source="images/manual-application-information.png" alt-text="アプリケーション情報の選択を手動で指定するスクリーンショット。" lightbox="images/manual-application-information.png":::
3. ウィザードの [ソフトウェア センター] 画面で [ **次へ** ] を選択します。
4. [展開の種類] で、[ **追加**] をクリックします。
5. [ **手動] を選択してデプロイの種類情報を指定** し、[ **次へ**] を選択します。
6. スクリプトデプロイに名前を付けて、[ **次へ**] を選択します。

   :::image type="content" source="images/manual-deployment-information.png" alt-text="スクリプトのデプロイ情報を指定するスクリーンショット。":::
7. この手順では、コンテンツが配置されている UNC パスをコピーします。 例: `\\ServerName\h$\SOFTWARE_SOURCE\path`。

   :::image type="content" source="images/deployment-type-wizard.png" alt-text="UNC パスのコピーを示すスクリーンショット。":::
  
8. さらに、インストール プログラムとして次を設定します。

     ```powershell
      Powershell.exe -ExecutionPolicy ByPass -File install.ps1 -RemoveMMA <workspace ID> -OnboardingScript .\WindowsDefenderATPOnboardingScript.cmd 
     ```

      **[次へ**] をクリックし、このセクションに独自のワークスペース ID を追加してください。
9. [ **次へ** ] をクリックし、[句の追加] をクリックします。
10. 検出方法は、次に示すレジストリ キーに基づいています。
      `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Sense`

      オプションを確認します。 **このレジストリ設定は、このアプリケーションの存在を示すためにターゲット システムで終了する必要があります。**

      :::image type="content" source="images/detection-wizard.png" alt-text="検出の種類ウィザードを示すスクリーンショット":::

      >[!TIP]
      >レジストリ キーの値は、統合ソリューションがインストールされているデバイスで、次に示す Powershell コマンドを実行して取得されました。 他のクリエイティブな検出方法も使用できます。 目標は、統合ソリューションが特定のデバイスに既にインストールされているかどうかを特定することです。 [値] フィールドと [データ型] フィールドは空白のままにできます。

     ```powershell
      get-wmiobject Win32_Product | Sort-Object -Property Name |Format-Table IdentifyingNumber, Name, LocalPackage -AutoSize 
     ```

11. [ **ユーザー エクスペリエンス** ] セクションで、スクリーンショットに示されている推奨設定を確認します。 環境に合わせて選択し、[ **次へ**] をクリックできます。 **インストール プログラムを表示するには**、フェーズ テスト中に **Normal** を使用してインストールしてから、一般的な展開のために **最小化** に変更することをお勧めします。

     >[!TIP]
     >許容される最大ランタイムを、(既定の) 120 分から 60 分に引き下げます。

     :::image type="content" source="images/user-experience-in-deployment-type-wizard.png" alt-text="展開の種類ウィザードでのユーザー エクスペリエンスを示すスクリーンショット。":::

12. その他の要件を追加し、[ **次へ**] を選択します。 
13. [依存関係] セクションで、[ **次へ**] を選択します。 
14. 完了画面が表示されるまで **[次へ** ]、[ **閉じる**] の順に選択します。
15. アプリケーション ウィザードが完了するまで **[次へ** ]を選択し続けます。 すべてが緑色でチェックされていることを確認します。
16. ウィザードを閉じて、最近作成したアプリケーションを右クリックし、下位レベルのサーバー コレクションに展開します。 ローカルでは、ソフトウェア センターでインストールを確認できます。 詳細については、CM ログの場所を `C:\Windows\CCM\Logs\AppEnforce.log`確認してください。

    :::image type="content" source="images/deploy-application.png" alt-text="作成されたアプリケーションのデプロイを示すスクリーンショット。" lightbox="images/deploy-application.png":::
     
17. MECM > Monitoring > Deployments で移行の状態を確認します。

    :::image type="content" source="images/deployment-status.png" alt-text="デプロイの状態チェックを示すスクリーンショット。" lightbox="images/deployment-status.png":::
      
18. トラブルシューティング。ETL ファイルが作成され、この場所 `C:\Windows\ccmcache\#\`の各サーバーに自動的にローカルに保存されます。 これらのファイルは、オンボードの問題のトラブルシューティングをサポートすることで利用できます。

## <a name="related-topics"></a>関連項目

- [Microsoft Monitoring Agent のセットアップ](/services-hub/health/mma-setup)
- [アプリケーションのデプロイ - Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-applications)
- [Microsoft Defender for Endpoint - Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)
- [Windows サーバーを Microsoft Defender for Endpoint にオンボードします](configure-server-endpoints.md)
- [Microsoft Defender for Endpoint: Windows Server 2012 R2 と 2016 の防御](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/defending-windows-server-2012-r2-and-2016/ba-p/2783292)

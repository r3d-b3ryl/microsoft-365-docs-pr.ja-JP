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
ms.openlocfilehash: fef1a5a7b8e47c4f97d36d4002ccf00401948d12
ms.sourcegitcommit: 2aa5c026cc06ed39a9c1c2bcabd1f563bf5a1859
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2022
ms.locfileid: "66994537"
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
- WINDOWS SERVER 2012 R2 や MMA エージェントを使用したWindows Server 2016などの下位レベルのサーバーを含むデバイス コレクションは、MECM インスタンスに設定されます。

一覧表示されている前提条件のインストールの詳細については、 [関連トピック](#related-topics) のセクションを参照してください。

## <a name="gather-required-files"></a>必要なファイルを収集する

統合ソリューション パッケージ、オンボード スクリプト、移行スクリプトを、MECM を使用して他のアプリをデプロイするのと同じコンテンツ ソースにコピーします。

1. オンボード スクリプトと統合ソリューションを[Microsoft 365 Defender設定ページ](https://sip.security.microsoft.com/preferences2/onboarding)からダウンロードします。
      :::image type="content" source="images/onboarding-script.png" alt-text="オンボード スクリプトと統合ソリューションのダウンロードのスクリーンショット。" lightbox="images/onboarding-script.png":::
2. ドキュメントから移行スクリプトをダウンロードします。[前の MMA ベースのMicrosoft Defender for Endpoint ソリューションのサーバー移行シナリオ](server-migration.md)。 このスクリプトは GitHub: [GitHub - microsoft/mdefordownlevelserver でも確認](https://github.com/microsoft/mdefordownlevelserver)できます。
3. MECM によってソフトウェア ソースとして使用される共有フォルダーに 3 つのファイルをすべて保存します。
     :::image type="content" source="images/ua-migration.png" alt-text="MECM によって共有フォルダーを保存するスクリーンショット。":::

## <a name="create-the-package-as-an-application"></a>アプリケーションとしてパッケージを作成する

1. MECM コンソールで、 **ソフトウェア ライブラリ>アプリケーション>アプリケーションの作成** の手順に従います。
2. [ **手動でアプリケーション情報を指定する] を選択します**。
      :::image type="content" source="images/manual-application-information.png" alt-text="アプリケーション情報の選択を手動で指定するスクリーンショット。" lightbox="images/manual-application-information.png":::
3. ウィザードの [ソフトウェア センター] 画面で [ **次へ** ] をクリックします。
4. [展開の種類] で、[ **追加**] をクリックします。
5. [ **手動] を選択して展開の種類情報を指定** し、[ **次へ**] をクリックします。
6. スクリプトデプロイに名前を付けて、[ **次へ**] をクリックします。
     :::image type="content" source="images/manual-deployment-information.png" alt-text="スクリプトのデプロイ情報を指定するスクリーンショット。":::
7. この手順では、コンテンツが配置されている UNC パスをコピーします。 例: `\\Cm1\h$\SOFTWARE_SOURCE\UAmigrate`。
     :::image type="content" source="images/deployment-type-wizard.png" alt-text="UNC パスのコピーを示すスクリーンショット。":::
8. さらに、インストール プログラムとして次を設定します。

     ```powershell
       Powershell.exe -ExecutionPolicy ByPass -File install.ps1 -Log -Etl -RemoveMMA 48594f03-7e66-4e15-8b60-d9da2f92d564 -OnboardingScript .\WindowsDefenderATP.onboarding
     ```

9. [ **次へ** ] をクリックし、[句の追加] をクリックします。
10. 句はレジストリ内で検索され、次のキーが存在するかどうかを確認します。  `HKEY_LOCAL_MACHINESOFTWARE\Classes\Installer\Products\63FAD065BFFD18F1926692665F704C6D`

     次の入力を指定します。
     - 値: **ProductName**
     - データ型 : **String**
     - オプションを確認します。 **このレジストリ設定は、このアプリケーションの存在を示すためにターゲット システムで終了する必要があります。**

     :::image type="content" source="images/detection-rule-wizard.png" alt-text="レジストリ キーの検出を示すスクリーンショット。":::

     >[!TIP]
     >このレジストリ キーの値は、統合ソリューションがインストールされているデバイスで次の PowerShell コマンドを実行することで取得されました。 他のクリエイティブな検出方法も使用できます。 目標は、統合ソリューションが特定のデバイスに既にインストールされているかどうかを識別することです。

     ```powershell
     PowerShell Cmd:  get-wmiobject Win32_Product | Sort-Object -Property Name |Format-Table IdentifyingNumber, Name, LocalPackage -AutoSize
     ```

11. [ **ユーザー エクスペリエンス** ] セクションでは、環境に合った内容を選択し、[ **次へ**] をクリックできます。 **インストール プログラムを表示するには**、フェーズ テスト中に **通常の可視性** を使用してインストールしてから、一般的な展開のために **最小化** に変更することをお勧めします。
     >[!TIP]
     > 許可される最大ランタイムは、(既定の) 120 分から 30 分に引き下げることが可能です。

     :::image type="content" source="images/user-experience-in-deployment-type-wizard.png" alt-text="展開の種類ウィザードでのユーザー エクスペリエンスを示すスクリーンショット。":::

12. [要件] で **[次へ** ] をクリックします。
13. [依存関係] で **[次へ** ] をクリックします。
14. 完了画面が表示されるまで **[次へ** ] をクリックし、[ **閉じる**] をクリックします。
15. アプリケーション ウィザードが完了するまで、次をクリックし続けます。 すべてが緑色でチェックされていることを確認します。
16. ウィザードを閉じて、最近作成したアプリケーションを右クリックし、下位レベルのサーバー コレクションに展開します。
     :::image type="content" source="images/deploy-application.png" alt-text="作成されたアプリケーションのデプロイを示すスクリーンショット。" lightbox="images/deploy-application.png":::
17. MECM>監視>デプロイで、この移行の状態を確認します。

      :::image type="content" source="images/deployment-status.png" alt-text="デプロイの状態チェックを示すスクリーンショット。" lightbox="images/deployment-status.png":::

## <a name="related-topics"></a>関連項目

- [Microsoft Monitoring Agent のセットアップ](/services-hub/health/mma-setup)
- [アプリケーションのデプロイ - Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-applications)
- [Microsoft Defender for Endpoint - Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)
- [Windows サーバーを Microsoft Defender for Endpoint にオンボードします](configure-server-endpoints.md)
- [Microsoft Defender for Endpoint: Windows Server 2012 R2 と 2016 の防御](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/defending-windows-server-2012-r2-and-2016/ba-p/2783292)

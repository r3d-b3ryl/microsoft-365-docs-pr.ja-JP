---
title: Microsoft エンドポイント マネージャーを使用したオンボーディング
description: Microsoft エンドポイント マネージャーを使用してMicrosoft Defender for Endpointにオンボードする方法について説明します
keywords: オンボード, 構成, デプロイ, デプロイ, エンドポイント マネージャー, Microsoft Defender for Endpoint, コレクションの作成, エンドポイント検出応答, 次世代保護, 攻撃面の削減, Microsoft エンドポイント マネージャー
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ca4c3e4992e9beb10e9369aede9d5ad8b9d73709
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466985"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャーを使用したオンボーディング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

この記事は、デプロイ ガイドの一部であり、オンボード方法の例として機能します。

[計画](deployment-strategy.md)のトピックでは、デバイスをサービスにオンボードするためのいくつかの方法が用意されています。 このトピックでは、クラウドネイティブ アーキテクチャについて説明します。

:::image type="content" source="images/cloud-native-architecture.png" alt-text="クラウドネイティブ アーキテクチャ" lightbox="images/cloud-native-architecture.png":::
*環境アーキテクチャの図*

Defender for Endpoint ではさまざまなエンドポイントとツールのオンボードがサポートされていますが、この記事ではそれらを取り上げません。 サポートされているその他のデプロイ ツールと方法を使用した一般的なオンボードの詳細については、 [オンボードの概要に関するページを](onboarding.md)参照してください。

[Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview) は、複数のサービスを統合するソリューション プラットフォームです。 [これには、Microsoft Intune](/mem/intune/fundamentals/what-is-intune) ベースのデバイス管理が含まれます。

このトピックでは、次のユーザーについて説明します。

- 手順 1: Microsoft エンドポイント マネージャー (MEM) でグループを作成してデバイスをサービスにオンボードし、構成を割り当てる
- 手順 2: Microsoft エンドポイント マネージャーを使用して Defender for Endpoint 機能を構成する

このオンボードガイダンスでは、Microsoft エンドポイント マネージャーを使用する場合に実行する必要がある次の基本的な手順について説明します。

- [ターゲット デバイスまたはユーザーの識別](#identify-target-devices-or-users)
  - Azure Active Directory グループの作成 (ユーザーまたはデバイス)
- [構成プロファイルの作成](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)
  - Microsoft エンドポイント マネージャーでは、機能ごとに個別のポリシーを作成する方法について説明します。

## <a name="resources"></a>リソース

残りのプロセスに必要なリンクを次に示します。

- [MEM ポータル](https://aka.ms/memac)
- [Microsoft 365 Defender](https://security.microsoft.com)
- [Intune セキュリティ ベースライン](/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

Microsoft エンドポイント マネージャーの詳細については、次のリソースを参照してください。

- [Microsoft エンドポイント マネージャー ページ](/mem/)
- [Intuneと ConfigMgr の収束に関するブログ投稿](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [MEM の概要ビデオ](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a>手順 1: MEM にグループを作成してデバイスをオンボードし、次の構成を割り当てる

### <a name="identify-target-devices-or-users"></a>ターゲット デバイスまたはユーザーを識別する

このセクションでは、構成を割り当てるテスト グループを作成します。

> [!NOTE]
> Intune では、デバイスとユーザーの管理に Azure Active Directory (Azure AD) のグループが使用されます。 Intune 管理者は、組織のニーズに合ったグループを設定できます。
>
> 詳細については、「[ユーザーとデバイスを整理するためのグループを追加する](/mem/intune/fundamentals/groups-add)」を参照してください。

### <a name="create-a-group"></a>グループを作成する

1. MEM ポータルを開きます。

2. **新しいグループ>グループを** 開きます。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/66f724598d9c3319cba27f79dd4617a4.png" alt-text="Microsoft エンドポイント マネージャー portal1" lightbox="images/66f724598d9c3319cba27f79dd4617a4.png":::

3. 詳細を入力し、新しいグループを作成します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/b1e0206d675ad07db218b63cd9b9abc3.png" alt-text="Microsoft エンドポイント マネージャー portal2" lightbox="images/b1e0206d675ad07db218b63cd9b9abc3.png":::

4. テスト ユーザーまたはデバイスを追加します。

5. [ **グループ] > [すべてのグループ** ] ウィンドウで、新しいグループを開きます。

6. **メンバーの追加>メンバー** を選択します。

7. テスト ユーザーまたはデバイスを見つけて選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/149cbfdf221cdbde8159d0ab72644cd0.png" alt-text="Microsoft エンドポイント マネージャー portal3" lightbox="images/149cbfdf221cdbde8159d0ab72644cd0.png":::

8. これで、テスト グループにテストするメンバーが追加されました。

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a>手順 2: Microsoft Defender for Endpoint機能を構成する構成ポリシーを作成する

次のセクションでは、いくつかの構成ポリシーを作成します。

1 つ目は、Defender for Endpoint にオンボードするユーザーまたはデバイスのグループを選択するための構成ポリシーです。

- [エンドポイントでの検出と対応](#endpoint-detection-and-response)

次に、さまざまな種類のエンドポイント セキュリティ ポリシーを作成し続けます。

- [次世代の保護](#next-generation-protection)
- [攻撃面の減少](#attack-surface-reduction---attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a>エンドポイントの検出および応答

1. MEM ポータルを開きます。

2. **エンドポイントのセキュリティ>エンドポイントの検出と応答** に移動します。 [ **プロファイルの作成**] をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/58dcd48811147feb4ddc17212b7fe840.png" alt-text="Microsoft エンドポイント マネージャー portal4" lightbox="images/58dcd48811147feb4ddc17212b7fe840.png":::

3. [**プラットフォーム] で、[Windows 10以降] を選択し、[プロファイル - エンドポイントの検出と応答] > [作成] を選択** します。

4. 名前と説明を入力し、[  **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/a5b2d23bdd50b160fef4afd25dda28d4.png" alt-text="Microsoft エンドポイント マネージャー portal5" lightbox="images/a5b2d23bdd50b160fef4afd25dda28d4.png":::

5. 必要に応じて設定を選択し、[  **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/cea7e288b5d42a9baf1aef0754ade910.png" alt-text="Microsoft エンドポイント マネージャー portal6" lightbox="images/cea7e288b5d42a9baf1aef0754ade910.png":::

    > [!NOTE]
    > このインスタンスでは、Defender for Endpoint が既にIntuneと統合されているため、これが自動的に設定されています。 統合の詳細については、「[IntuneでMicrosoft Defender for Endpointを有効にする」を](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)参照してください。
    >
    > 次の図は、Microsoft Defender for EndpointがIntuneと統合されていない場合に表示される例です。
    >
    > :::image type="content" source="images/2466460812371ffae2d19a10c347d6f4.png" alt-text="Microsoft エンドポイント マネージャー portal7" lightbox="images/2466460812371ffae2d19a10c347d6f4.png":::

6. 必要に応じてスコープ タグを追加し、[  **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ef844f52ec2c0d737ce793f68b5e8408.png" alt-text="Microsoft エンドポイント マネージャー portal8" lightbox="images/ef844f52ec2c0d737ce793f68b5e8408.png":::

7. [グループの **選択]** をクリックしてテスト グループを追加し、グループを選択してから、[  **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/fc3525e20752da026ec9f46ab4fec64f.png" alt-text="Microsoft エンドポイント マネージャー portal9" lightbox="images/fc3525e20752da026ec9f46ab4fec64f.png":::

8. 確認して同意し、[  **作成**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/289172dbd7bd34d55d24810d9d4d8158.png" alt-text="Microsoft エンドポイント マネージャー portal10" lightbox="images/289172dbd7bd34d55d24810d9d4d8158.png":::

9. 完了したポリシーを表示できます。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/5a568b6878be8243ea2b9d82d41ed297.png" alt-text="Microsoft エンドポイント マネージャー portal11" lightbox="images/5a568b6878be8243ea2b9d82d41ed297.png":::

### <a name="next-generation-protection"></a>次世代の保護

1. MEM ポータルを開きます。

2. **Endpoint Security >ウイルス対策>ポリシーの作成** に移動します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/6b728d6e0d71108d768e368b416ff8ba.png" alt-text="Microsoft エンドポイント マネージャー portal12" lightbox="images/6b728d6e0d71108d768e368b416ff8ba.png":::

3. **プラットフォーム - Windows 10 以降 - Windowsとプロファイル - Microsoft Defender ウイルス対策 >作成** を選択します。

4. 名前と説明を入力し、[  **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/a7d738dd4509d65407b7d12beaa3e917.png" alt-text="Microsoft エンドポイント マネージャー portal13" lightbox="images/a7d738dd4509d65407b7d12beaa3e917.png":::

5. [**構成の設定] ページ** で、Microsoft Defender ウイルス対策に必要な構成を設定します (Cloud Protection、Exclusions、Real-Time Protection、修復)。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/3840b1576d6f79a1d72eb14760ef5e8c.png" alt-text="Microsoft エンドポイント マネージャー portal14" lightbox="images/3840b1576d6f79a1d72eb14760ef5e8c.png":::

6. 必要に応じてスコープ タグを追加し、[  **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/2055e4f9b9141525c0eb681e7ba19381.png" alt-text="Microsoft エンドポイント マネージャー ポータル15" lightbox="images/2055e4f9b9141525c0eb681e7ba19381.png":::

7. 含めるグループを選択し、テスト グループに割り当ててから、[  **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/48318a51adee06bff3908e8ad4944dc9.png" alt-text="Microsoft エンドポイント マネージャー portal16" lightbox="images/48318a51adee06bff3908e8ad4944dc9.png":::

8. 確認して作成し、  **作成** を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/dfdadab79112d61bd3693d957084b0ec.png" alt-text="Microsoft エンドポイント マネージャー portal17" lightbox="images/dfdadab79112d61bd3693d957084b0ec.png":::

9. 作成した構成ポリシーが表示されます。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/38180219e632d6e4ec7bd25a46398da8.png" alt-text="Microsoft エンドポイント マネージャー portal18" lightbox="images/38180219e632d6e4ec7bd25a46398da8.png":::

### <a name="attack-surface-reduction---attack-surface-reduction-rules"></a>攻撃面の縮小 - 攻撃面の縮小ルール

1. MEM ポータルを開きます。

2. **[エンドポイント セキュリティ] > [攻撃面の縮小**] に移動します。

3. [  **ポリシーの作成**] を選択します。

4. [**プラットフォーム - Windows 10以降 - プロファイル - 攻撃面の縮小ルール] > [作成**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/522d9bb4288dc9c1a957392b51384fdd.png" alt-text="Microsoft エンドポイント マネージャー portal19" lightbox="images/522d9bb4288dc9c1a957392b51384fdd.png":::

5. 名前と説明を入力し、[  **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png" alt-text="Microsoft エンドポイント マネージャー portal20" lightbox="images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png":::

6. [ **構成の設定] ページ** で、攻撃面の縮小ルールに必要な構成を設定し、[  **次へ**] を選択します。

    > [!NOTE]
    > 攻撃面の縮小ルールをすべて監査に構成します。
    >
    > 詳細については、「 [攻撃面の縮小ルール](attack-surface-reduction.md)」を参照してください。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/dd0c00efe615a64a4a368f54257777d0.png" alt-text="Microsoft エンドポイント マネージャー portal21" lightbox="images/dd0c00efe615a64a4a368f54257777d0.png":::

7. 必要に応じてスコープ タグを追加し、[  **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/6daa8d347c98fe94a0d9c22797ff6f28.png" alt-text="Microsoft エンドポイント マネージャー portal22" lightbox="images/6daa8d347c98fe94a0d9c22797ff6f28.png":::

8. 含めるグループを選択し、テスト グループに割り当ててから、[  **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/45cefc8e4e474321b4d47b4626346597.png" alt-text="Microsoft エンドポイント マネージャー portal23" lightbox="images/45cefc8e4e474321b4d47b4626346597.png":::

9. 詳細を確認し、[  **作成**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/2c2e87c5fedc87eba17be0cdeffdb17f.png" alt-text="Microsoft エンドポイント マネージャー portal24" lightbox="images/2c2e87c5fedc87eba17be0cdeffdb17f.png":::

10. ポリシーを表示します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/7a631d17cc42500dacad4e995823ffef.png" alt-text="Microsoft エンドポイント マネージャー portal25" lightbox="images/7a631d17cc42500dacad4e995823ffef.png":::

### <a name="attack-surface-reduction---web-protection"></a>攻撃面の縮小 - Web 保護

1. MEM ポータルを開きます。

2. **[エンドポイント セキュリティ] > [攻撃面の縮小**] に移動します。

3. [  **ポリシーの作成**] を選択します。

4. **[Windows 10以降 - Web 保護>作成**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png" alt-text="Microsoft エンドポイント マネージャー portal26" lightbox="images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png":::

5. 名前と説明を入力し、[  **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/5be573a60cd4fa56a86a6668b62dd808.png" alt-text="Microsoft エンドポイント マネージャー portal27" lightbox="images/5be573a60cd4fa56a86a6668b62dd808.png":::

6. [ **構成設定] ページ** で、Web Protection に必要な構成を設定し、[  **次へ**] を選択します。

    > [!NOTE]
    > Web Protection をブロックするように構成しています。
    >
    > 詳細については、「 [Web 保護](web-protection-overview.md)」を参照してください。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/6104aa33a56fab750cf30ecabef9f5b6.png" alt-text="Microsoft エンドポイント マネージャー portal28" lightbox="images/6104aa33a56fab750cf30ecabef9f5b6.png":::

7. **必要に応じてスコープ タグを追加>次へ**。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/6daa8d347c98fe94a0d9c22797ff6f28.png" alt-text="Microsoft エンドポイント マネージャー portal29" lightbox="images/6daa8d347c98fe94a0d9c22797ff6f28.png":::

8. [ **テスト グループに割り当てる] > [次へ] を** 選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/45cefc8e4e474321b4d47b4626346597.png" alt-text="Microsoft エンドポイント マネージャー portal30" lightbox="images/45cefc8e4e474321b4d47b4626346597.png":::

9. [ **確認と作成] > [作成**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/8ee0405f1a96c23d2eb6f737f11c1ae5.png" alt-text="Microsoft エンドポイント マネージャー portal31" lightbox="images/8ee0405f1a96c23d2eb6f737f11c1ae5.png":::

10. ポリシーを表示します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/e74f6f6c150d017a286e6ed3dffb7757.png" alt-text="Microsoft エンドポイント マネージャー portal32" lightbox="images/e74f6f6c150d017a286e6ed3dffb7757.png":::

## <a name="validate-configuration-settings"></a>構成設定を検証する

### <a name="confirm-policies-have-been-applied"></a>ポリシーが適用されたことを確認する

構成ポリシーが割り当てられると、適用に時間がかかります。

タイミングの詳細については、「[Intune構成情報](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)」を参照してください。

構成ポリシーがテスト デバイスに適用されたことを確認するには、構成ポリシーごとに次の手順に従います。

1. 上の手順に従って、MEM ポータルを開き、関連するポリシーに移動します。 次の例は、次世代の保護設定を示しています。

    > [!div class="mx-imgBorder"]
    > [![Microsoft エンドポイント マネージャー portal33 の画像。](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox) 

2. **構成ポリシー** を選択して、ポリシーの状態を表示します。

    > [!div class="mx-imgBorder"]
    > [![Microsoft エンドポイント マネージャー portal34 の画像。](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)

3. [  **デバイスの状態]** を選択して状態を表示します。

    > [!div class="mx-imgBorder"]
    > [![Microsoft エンドポイント マネージャー portal35 の画像。](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)

4. **[ユーザーの状態]** を選択して状態を表示します。

    > [!div class="mx-imgBorder"]
    > [![Microsoft エンドポイント マネージャー portal36 の画像。](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)

5. **[設定ごとの状態**] を選択して状態を表示します。

    > [!TIP]
    > このビューは、別のポリシーと競合するすべての設定を識別するのに非常に便利です。

    > [!div class="mx-imgBorder"]
    > [![Microsoft エンドポイント マネージャー portal37 の画像。](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)

### <a name="confirm-endpoint-detection-and-response"></a>エンドポイントでの検出と対応を確認する

1. 構成を適用する前に、Defender for Endpoint Protection サービスを開始しないでください。

    > [!div class="mx-imgBorder"]
    > [![[サービス] パネル 1 の画像。](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)

2. 構成が適用されたら、Defender for Endpoint Protection Service を開始する必要があります。

    > [!div class="mx-imgBorder"]
    > [![[サービス] パネル 2 の画像。](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)

3. サービスがデバイスで実行されると、デバイスがポータルMicrosoft 365 Defender表示されます。

    > [!div class="mx-imgBorder"]
    > [![Microsoft 365 Defender ポータルの画像。](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)

### <a name="confirm-next-generation-protection"></a>次世代の保護を確認する

1. テスト デバイスにポリシーを適用する前に、次に示すように設定を手動で管理できる必要があります。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/88efb4c3710493a53f2840c3eac3e3d3.png" alt-text="[設定] ページ -1" lightbox="images/88efb4c3710493a53f2840c3eac3e3d3.png":::

2. ポリシーが適用されたら、設定を手動で管理することはできません。

    > [!NOTE]
    > 次の図では、 **クラウド配信保護を有効に** し、 **リアルタイム保護を有効にすると** 、管理として表示されます。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/9341428b2d3164ca63d7d4eaa5cff642.png" alt-text="[設定] ページ -2" lightbox="images/9341428b2d3164ca63d7d4eaa5cff642.png":::

### <a name="confirm-attack-surface-reduction---attack-surface-reduction-rules"></a>攻撃面の縮小の確認 - 攻撃面の縮小ルール

1. テスト デバイスにポリシーを適用する前に、PowerShell ウィンドウをペンで入力します `Get-MpPreference`。

2. これは、コンテンツを含まない次の行で応答する必要があります。

    > AttackSurfaceReductionOnlyExclusions:
    >
    > AttackSurfaceReductionRules_Actions:
    >
    > AttackSurfaceReductionRules_Ids:

    :::image type="content" source="images/cb0260d4b2636814e37eee427211fe71.png" alt-text="コマンド ライン 1" lightbox="images/cb0260d4b2636814e37eee427211fe71.png":::

3. テスト デバイスにポリシーを適用した後、PowerShell Windowsを開き、「.」と入力します`Get-MpPreference`。

4. 次に示すように、これは次の行で応答する必要があります。

   :::image type="content" source="images/619fb877791b1fc8bc7dfae1a579043d.png" alt-text="コマンド ライン 2" lightbox="images/619fb877791b1fc8bc7dfae1a579043d.png":::

### <a name="confirm-attack-surface-reduction---web-protection"></a>攻撃面の縮小を確認する - Web 保護

1. テスト デバイスで PowerShell Windowsを開き、「.」と入力します`(Get-MpPreference).EnableNetworkProtection`。

2. 次に示すように、これは 0 で応答する必要があります。

   :::image type="content" source="images/196a8e194ac99d84221f405d0f684f8c.png" alt-text="コマンド ライン 3" lightbox="images/196a8e194ac99d84221f405d0f684f8c.png":::

3. ポリシーを適用した後、PowerShell Windowsを開き、「.」と入力します`(Get-MpPreference).EnableNetworkProtection`。

4. 次に示すように、これは 1 で応答する必要があります。

   :::image type="content" source="images/c06fa3bbc2f70d59dfe1e106cd9a4683.png" alt-text="コマンド ライン 4" lightbox="images/c06fa3bbc2f70d59dfe1e106cd9a4683.png":::

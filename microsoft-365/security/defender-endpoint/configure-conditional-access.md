---
title: Microsoft Defender for Endpointで条件付きアクセスを構成する
description: 条件付きアクセスを実装するためにIntune、Microsoft 365 Defender、Azure で行う必要がある手順について説明します
keywords: 条件付きアクセス, 条件付き, アクセス, デバイス リスク, リスク レベル, 統合, Intune 統合
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b476cc6085c3ec65d638a77e34444d687a86aa11
ms.sourcegitcommit: 34910ea9318289d78c35b0e7990238467c05384b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67306462"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointで条件付きアクセスを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

このセクションでは、条件付きアクセスを適切に実装するために必要なすべての手順について説明します。

## <a name="before-you-begin"></a>はじめに

> [!WARNING]
> このシナリオでは、Azure AD 登録済みデバイスはサポートされないことに注意してください。</br>
> Intune登録済みデバイスのみがサポートされます。

すべてのデバイスがIntuneに登録されていることを確認する必要があります。 次のいずれかのオプションを使用して、デバイスをIntuneに登録できます。

- IT 管理: 自動登録を有効にする方法の詳細については、「[Windows](/intune/windows-enroll#enable-windows-10-automatic-enrollment) 登録」を参照してください
- エンド ユーザー: IntuneにWindows 10デバイスとWindows 11 デバイスを登録する方法の詳細については、「Windows 10 [デバイスをIntuneに登録](/intune/quickstart-enroll-windows-device)する」を参照してください。
- エンド ユーザーの代替手段: Azure AD ドメインへの参加の詳細については、「 [方法: Azure AD 参加の実装を計画する」を参照してください](/azure/active-directory/devices/azureadjoin-plan)。

Microsoft 365 Defender、Intune ポータル、Azure AD portal で実行する必要がある手順があります。

これらのポータルにアクセスし、条件付きアクセスを実装するために必要なロールに注意することが重要です。

- **Microsoft 365 Defender** - 統合を有効にするには、グローバル管理者ロールを使用してポータルにサインインする必要があります。
- **Intune** - 管理アクセス許可を持つセキュリティ管理者権限でポータルにサインインする必要があります。
- **Azure AD portal** - グローバル管理者、セキュリティ管理者、または条件付きアクセス管理者としてサインインする必要があります。

> [!NOTE]
> Microsoft Intune環境が必要です。Intuneマネージドデバイスと Azure AD がWindows 10デバイスとWindows 11デバイスに参加しています。

条件付きアクセスを有効にするには、次の手順に従います。

- 手順 1: Microsoft 365 DefenderからMicrosoft Intune接続を有効にする
- 手順 2: Intuneで Defender for Endpoint 統合を有効にする
- 手順 3: Intuneでコンプライアンス ポリシーを作成する
- 手順 4: ポリシーを割り当てる 
- 手順 5: Azure AD 条件付きアクセス ポリシーを作成する

### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>手順 1: Microsoft Intune接続を有効にする

1. ナビゲーション ウィンドウで、[**Settings** \> **Endpoints** \> **General** \> **Advanced features** \> **Microsoft Intune connection**] を選択します。
2. Microsoft Intune設定を **[オン]** に切り替えます。
3. [ **保存] 環境設定をクリックします**。

### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>手順 2: Intuneで Defender for Endpoint 統合を有効にする

1. Azure portal
2. [ **デバイス コンプライアンス** \> **] Microsoft Defender ATP** を選択します。
3. **[Connect Windows 10.0.15063+ デバイス] を [Microsoft Defender Advanced Threat Protection] に** **[オン]** に設定します。
4. **[保存]** をクリックします。

### <a name="step-3-create-the-compliance-policy-in-intune"></a>手順 3: Intuneでコンプライアンス ポリシーを作成する

1. [Azure portal](https://portal.azure.com)で、[**すべてのサービス**] を選択し、**Intune** でフィルター処理して **、[Microsoft Intune**] を選択します。
2. [ **デバイス コンプライアンス** \> **ポリシーの** \> **作成ポリシー**] を選択します。
3. 名前と **説明** を入力 **します**。
4. **プラットフォーム** で、**Windows 10以降を** 選択します。
5. **[デバイスの正常性**] 設定 **で、[デバイスの脅威レベル] または [デバイスの脅威レベル] の下にあるデバイスを** 好みのレベルに設定します。

   - **[セキュリティ保護]**: このレベルはセキュリティ上最も安全です。 デバイスに既存の脅威を持つことはできません。それでも会社のリソースにアクセスできます。 いずれかの脅威が見つかった場合、デバイスは非準拠と評価されます。
   - **[低]**: 低レベルの脅威が存在する場合にのみ、デバイスは準拠しています。 脅威レベルが中程度または高いデバイスは準拠していません。
   - **[中]**: デバイスに存在する脅威が低または中の場合、デバイスは準拠しています。 高レベルの脅威が検出された場合は、デバイスは非準拠と判定されます。
   - **高**: このレベルは安全性が最も低く、すべての脅威レベルを許可します。 そのため、脅威レベルが高い、中、低のデバイスは準拠していると見なされます。

6. **[OK] を** 選択し、[**作成]** を選択して変更を保存します (ポリシーを作成します)。

### <a name="step-4-assign-the-policy"></a>手順 4: ポリシーを割り当てる

1. [Azure portal](https://portal.azure.com)で、[**すべてのサービス**] を選択し、**Intune** でフィルター処理して **、[Microsoft Intune**] を選択します。
2. [**デバイス コンプライアンス** \> **ポリシー**] を選択>、Microsoft Defender for Endpointコンプライアンス ポリシーを選択します。
3. **[割り当て]** を選択します。
4. ポリシーを割り当てるには、Azure AD グループを含めるか除外します。
5. ポリシーをグループに展開するには、[保存] を選択 **します**。 ポリシーの対象となるユーザー デバイスは、コンプライアンスについて評価されます。

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>手順 5: Azure AD 条件付きアクセス ポリシーを作成する

1. [Azure portal](https://portal.azure.com)で、**Azure Active Directory** \> **条件付きアクセス** \> **の新しいポリシーを** 開きます。
2. ポリシー **名** を入力し、[ **ユーザーとグループ**] を選択します。 含めるオプションまたは除外するオプションを使用して、ポリシーのグループを追加し、**[完了]** を選択します。
3. **クラウド アプリ** を選択し、保護するアプリを選択します。 たとえば、**[アプリを選択]** を選び、**[Office 365 SharePoint Online]** と **[Office 365 Exchange Online]** を選択します。 [**完了**] を選んで変更内容を保存します。

4. **[条件** \> **クライアント アプリ**] を選択して、アプリとブラウザーにポリシーを適用します。 たとえば、**[はい]** を選択し、**[ブラウザー]** と **[モバイル アプリとデスクトップ クライアント]** を有効にします。 [**完了**] を選んで変更内容を保存します。

5. **[許可]** を選択し、デバイスのコンプライアンスに基づいて条件付きアクセスを適用します。 たとえば、[アクセス\>**を許可****するデバイスを準拠としてマークする]** を選択します。 **[選択]** を選んで変更を保存します。

6. **[ポリシーを有効にする]**、**[作成]** の順に選択して変更を保存します。

> [!NOTE]
> Microsoft Defender for Endpoint アプリをIntuneの承認済みクライアント アプリ ポリシーと共に使用して、デバイス コンプライアンス ポリシーと条件付きアクセス ポリシーを設定できます。 条件付きアクセスの設定中に、Microsoft Defender for Endpoint アプリに除外は必要ありません。 Android & iOS のMicrosoft Defender for Endpoint (アプリ ID - dd47d17a-3194-4d86-bfd5-c6ae6f5651e3) は承認されたアプリではありませんが、デバイスのセキュリティ体制を報告するアクセス許可があります。 このアクセス許可により、条件付きアクセスに対するコンプライアンス情報のフローが有効になります。
> この変更は、2022 年 9 月 30 日から利用できます。

詳細については、「[Intune で条件付きアクセスによる Microsoft Defender for Endpoint のコンプライアンスを強制する](/intune/advanced-threat-protection)」を参照してください。

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-belowfoldlink)

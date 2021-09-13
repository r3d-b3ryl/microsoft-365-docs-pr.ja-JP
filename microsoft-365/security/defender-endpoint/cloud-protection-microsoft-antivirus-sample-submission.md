---
title: クラウド保護とサンプル申請 (Microsoft Defender ウイルス対策
description: クラウドで提供される保護とセキュリティについてMicrosoft Defender ウイルス対策
keywords: Microsoft Defender ウイルス対策、次世代テクノロジ、ウイルス対策サンプル申請、次世代 AV、機械学習、マルウェア対策、セキュリティ、防御、クラウド、クラウド配信の保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 08/31/2021
ms.openlocfilehash: 5d9f6ace79d05eff795041732e045abf18d5f792
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192781"
---
# <a name="cloud-protection-and-sample-submission-in-microsoft-defender-antivirus"></a>クラウド保護とサンプル申請 (Microsoft Defender ウイルス対策

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender ウイルス対策

Microsoft Defender ウイルス対策は、マルウェアを検出するために多くのインテリジェントなメカニズムを使用します。 最も強力な機能の 1 つは、クラウドの機能を適用してマルウェアを検出し、迅速な分析を実行する機能です。 クラウド保護と自動サンプル申請は、新しい脅威やMicrosoft Defender ウイルス対策保護するために、ユーザーと共に機能します。 

疑わしいファイルや悪意のあるファイルが検出されると、分析のためにサンプルがクラウド サービスに送信され、Microsoft Defender ウイルス対策ブロックされます。 すぐに決定が行われたら、すぐにファイルが解放またはブロックMicrosoft Defender ウイルス対策。 

この記事では、クラウド保護と自動サンプル申請の概要について説明します。Microsoft Defender ウイルス対策。 クラウド保護の詳細については、「クラウド保護[とクラウド保護」を参照Microsoft Defender ウイルス対策。](cloud-protection-microsoft-defender-antivirus.md)

## <a name="how-cloud-protection-and-sample-submission-work-together"></a>クラウド保護とサンプル申請の機能

クラウド保護とサンプル申請の機能を理解するには、Defender for Endpoint が脅威から保護する方法を理解すると役立ちます。 Microsoft インテリジェント セキュリティ Graph、センサーの膨大なネットワークから脅威データを監視します。 Microsoft は、クライアントからの信号とインテリジェント セキュリティ Graph のセンサーとデータの膨大なネットワークに基づいてファイルを評価できるクラウドベースの機械学習モデルをレイヤー化します。 この方法により、Defender for Endpoint は、前に見たことない多くの脅威をブロックできます。 

次の図は、クラウド保護とサンプル申請のフローを示Microsoft Defender ウイルス対策。

:::image type="content" source="images/cloud-protection-flow.png" alt-text="クラウド配信の保護フロー":::

Microsoft Defender ウイルス対策クラウド保護は、次の方法を使用して、一目で見たことの少ないほとんどの新しい脅威を自動的にブロックします。

1. クライアント ベースの機械学習モデルを軽量にし、新しいマルウェアと未知のマルウェアをブロックします。

2. ローカルの動作分析、ファイル ベースの攻撃とファイルレス攻撃の停止。

3. 汎用的でヒューリスティックな手法を使用して一般的なマルウェアを検出する、高精度のウイルス対策。

4. 高度なクラウドベースの保護は、エンドポイントで実行Microsoft Defender ウイルス対策疑わしいファイルの意図を確認するために、より多くのインテリジェンスが必要な場合に提供されます。

   1. ユーザーが明確Microsoft Defender ウイルス対策判断できない場合は、ファイル メタデータがクラウド保護サービスに送信されます。 多くの場合、数ミリ秒以内に、クラウド保護サービスは、ファイルが悪意のあるものか脅威ではないかについてのメタデータに基づいて判断できます。  

      - ファイル メタデータのクラウド クエリは、動作、Web のマーク、または明確な判定が決定されないその他の特性の結果である可能性があります。
      - 小さなメタデータ ペイロードが送信され、マルウェアの評決に達するか、脅威ではないかという目的で送信されます。 メタデータには、個人を特定できる情報 (PII) は含められない。 ファイル名などの情報はハッシュ化されます。
      - 同期または非同期を指定できます。 同期の場合、クラウドが評決をレンダリングするまでファイルは開かれません。 非同期の場合、クラウド保護が分析を実行している間にファイルが開きます。
      - メタデータには、PE 属性、静的ファイル属性、動的属性、コンテキスト属性などがあります (「クラウド保護サービスに送信されるメタデータの例 [」を参照](#examples-of-metadata-sent-to-the-cloud-protection-service))。

   2. メタデータを調べた後Microsoft Defender ウイルス対策クラウド保護が決定的な評決に達できない場合は、ファイルのサンプルを要求して詳細な検査を行います。 この要求は、サンプル申請の設定構成を尊重します。

      1. **安全なサンプルを自動的に送信** する (既定)
         - セーフサンプルは、一般的に PII データが含まれていると見なされるサンプルです。.bat、.scr、.dll、.exe。
         - ファイルに PII が含まれている可能性がある場合、ユーザーはファイル サンプルの申請を許可する要求を取得します。
         - このオプションは、既定の Windows macOS、および Linux です。

      2. **常にプロンプトを表示する**
         - 構成されている場合、ユーザーは常にファイル提出前に同意を求めるメッセージが表示されます
         - この設定は macOS クラウド保護では使用できません

      3. **すべてのサンプルを自動的に送信する**
         - 構成されている場合、すべてのサンプルが自動的に送信されます
         - Word ドキュメントに埋め込まれたマクロを含めるサンプル申請を行う場合は、[すべてのサンプルを自動的に送信する] を選択する必要があります。
         - この設定は、macOS クラウド保護では使用できません

      4. **送信しない**
         - ファイル サンプル分析に基づいて "一目でブロックする" の防止
         - "送信しない" は、macOS ポリシーの "Disabled" 設定と同じです。
         - サンプル提出が無効になっている場合でも、検出用にメタデータが送信されます。

   3. メタデータやファイルがクラウド保護に送信された後、サンプル、起案、またはビッグ データ分析機械学習モデルを使用して、評決に達することができます。  クラウドによる保護をオフにした場合、分析は、ローカルの機械学習モデルや同様の機能を通じてクライアントが提供できる機能にのみ制限されます。

> [!IMPORTANT]
> [一目でブロック (BAFS)](configure-block-at-first-sight-microsoft-defender-antivirus.md) は、ファイルまたはプロセスが安全かどうかを判断する発発と分析を提供します。 BAFS は、評決に達するまで、ファイルの開き方を一瞬遅らせる可能性があります。 サンプル提出を無効にすると、BAFS も無効になり、ファイル分析はメタデータにのみ制限されます。 サンプル申請と BAFS を有効に保つことをお勧めします。 詳細については、「一目でブロック [する」を参照してください。](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)

## <a name="cloud-protection-levels"></a>クラウド保護レベル

クラウド保護は、既定ではクラウド保護でMicrosoft Defender ウイルス対策。 組織の保護レベルを構成することもできますが、クラウド保護を有効にすることをお勧めします。 「[クラウド配信の保護レベルを指定する」を参照Microsoft Defender ウイルス対策。](specify-cloud-protection-level-microsoft-defender-antivirus.md)

## <a name="sample-submission-settings"></a>サンプル申請の設定

クラウド保護レベルの構成に加えて、サンプル提出設定を構成できます。 次のいくつかのオプションから選択できます。

- **安全なサンプルを自動的に送信**  する (既定の動作)
- **すべてのサンプルを自動的に送信する**  
- **サンプルを送信しない**  

Intune、Configuration Manager、GPO、または PowerShell を使用した構成オプションの詳細については、「クラウド保護を有効にする」を参照[Microsoft Defender ウイルス対策。](enable-cloud-protection-microsoft-defender-antivirus.md)

## <a name="examples-of-metadata-sent-to-the-cloud-protection-service"></a>クラウド保護サービスに送信されるメタデータの例

:::image type="content" source="images/cloud-protection-metadata-sample.png" alt-text="図 2.Microsoft Defender Cloud Protection に送信されるメタデータの例":::

次の表に、クラウド保護によって分析のために送信されるメタデータの例を示します。

| 種類 | 属性 |
|:---|:---|
| コンピューターの属性 | `OS version` <br/> `Processor` <br/> `Security settings` |
| 動的属性とコンテキスト属性 | **プロセスとインストール** <br/> `ProcessName` <br/> `ParentProcess` <br/> `TriggeringSignature` <br/> `TriggeringFile` <br/> `Download IP and url` <br/> `HashedFullPath` <br/> `Vpath` <br/> `RealPath` <br/> `Parent/child relationships` <br/><br/>**動作** <br/> `Connection IPs` <br/> `System changes` <br/> `API calls` <br/> `Process injection` <br/><br/>**Locale** <br/> `Locale setting` <br/> `Geographical location` |
| 静的ファイル属性 | **部分ハッシュと完全ハッシュ** <br/> `ClusterHash` <br/> `Crc16` <br/> `Ctph` <br/> `ExtendedKcrcs` <br/> `ImpHash` <br/> `Kcrc3n` <br/> `Lshash` <br/> `LsHashs` <br/> `PartialCrc1` <br/> `PartialCrc2` <br/> `PartialCrc3` <br/> `Sha1` <br/> `Sha256` <br/><br/>**ファイルのプロパティ** <br/>`FileName` <br/> `FileSize` <br/><br/> **署名者情報** <br/> `AuthentiCodeHash` <br/> `Issuer` <br/> `IssuerHash` <br/> `Publisher` <br/> `Signer` <br/> `SignerHash` |

## <a name="samples-are-treated-as-customer-data"></a>サンプルは顧客データとして扱われる

サンプル提出で何が起こるか疑問に思う場合に備え、Defender for Endpoint は、すべてのファイル サンプルを顧客データとして扱います。 Microsoft は、Defender for Endpoint へのオンボーディング時に組織が選択した地理的およびデータ保持の両方の選択肢を尊重します。 

さらに、Defender for Endpoint は複数のコンプライアンス認定を受け、高度なコンプライアンス制御セットへの継続的な遵守を実証しています。

- ISO 27001
- ISO 27018
- SOC I、II、III
- および PCI

詳細については、以下のリソースをご覧ください。

- [Azure コンプライアンス オファリング](/azure/storage/common/storage-compliance-offerings) 
- [Service Trust Portal](https://servicetrust.microsoft.com)
- [Microsoft Defender for Endpoint データストレージとプライバシー](data-storage-privacy.md#data-storage-location)

## <a name="other-file-sample-submission-scenarios"></a>その他のファイルサンプル提出シナリオ

Defender for Endpoint が、クラウド保護に関連しないファイル サンプルを要求するシナリオは、さらに 2 Microsoft Defender ウイルス対策。 これらのシナリオについては、次の表で説明します。

| シナリオ | 説明 |
|:---|:---|
|ポータル内の手動ファイル サンプル コレクションMicrosoft 365 Defenderします。 | デバイスを Defender for Endpoint にオンボーディングする場合は、エンドポイント検出と応答[(EDR) の設定を構成できます](overview-endpoint-detection-response.md)。 たとえば、デバイスからのサンプル コレクションを有効にする設定があります。これは、この記事で説明するサンプル提出設定と簡単に混同できます。 <br/><br/>このEDR設定は、Microsoft 365 Defender ポータルから要求されたデバイスからのファイル サンプル コレクションを制御し、既に確立されている役割とアクセス許可の対象になります。 この設定では、エンドポイントからのファイルコレクションを許可またはブロックして、ポータルでの詳細な分析などの機能Microsoft 365 Defenderできます。 この設定が構成されていない場合、既定ではサンプル コレクションを有効にします。 <br/><br/>Defender for Endpoint 構成設定の詳細については、「Defender for Endpoint でのデバイスのオンボード ツール[とメソッドWindows 10」を参照してください。](configure-endpoints.md) |
| 自動調査と応答のコンテンツ分析 | 自動 [調査が](automated-investigations.md) デバイスで実行されている場合 (アラートに応答して自動的に実行するか、手動で実行するように構成されている場合)、疑わしいと識別されたファイルをエンドポイントから収集して、詳細な検査を行うことができます。 必要に応じて、自動調査用のファイル コンテンツ分析機能を、Microsoft 365 Defenderできます。 <br/><br/> ファイル拡張子の名前を変更して、自動調査中に自動的に提出される他のファイルの種類の拡張子を追加または削除することもできます。 <br/><br/> 詳細については、「オートメーション ファイルの [アップロードを管理する」を参照してください](manage-automation-file-uploads.md)。 |

## <a name="see-also"></a>関連項目

[次世代保護の概要](next-generation-protection.md)

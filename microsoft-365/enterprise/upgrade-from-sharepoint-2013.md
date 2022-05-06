---
title: SharePoint 2013 からのアップグレード
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 11/10/2021
audience: ITPro
ms.topic: conceptual
ms.prod: sharepoint-server-itpro
ms.collection:
- Ent_O365
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: SharePoint Server 2013 および SharePoint Foundation 2013 からアップグレードする情報とリソースを確認します。 2023 年 4 月 11 日の両方のサポート。
ms.openlocfilehash: 05f545b67d60d6bcc45587049e49a5f5c1f6d654
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889927"
---
# <a name="upgrading-from-sharepoint-2013"></a>SharePoint 2013 からのアップグレード

Microsoft SharePoint Server 2013 と SharePoint Foundation 2013 は **どちらも、2023 年 4 月 11** 日にサポートを終了します。 この記事では、既存のSharePoint サーバー データをMicrosoft 365で SharePoint Online に移行したり、オンプレミスの 2013 環境SharePointアップグレードしたりするのに役立つリソースを提供します。 この記事の残りの部分では、SharePoint 2013 を使用して、SharePoint Server 2013 と SharePoint Foundation 2013 の両方を参照します。

## <a name="what-is-end-of-support"></a>*サポートの終了* とは何ですか?

ほとんどの Microsoft 製品にはサポート ライフサイクルがあり、その間に新機能、バグ修正、セキュリティ修正などが行われます。 サポート終了日を経過しても、製品の動作は停止しませんが、Microsoft では次のものが提供されなくなります。

- 発生する可能性がある問題のテクニカル サポート。

- サーバーの安定性と使いやすさに影響を与える可能性がある問題に関するバグ修正。

- サーバーがセキュリティ違反に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

つまり、製品の更新プログラム、パッチ、修正プログラム (セキュリティ パッチや修正プログラムを含む) は今後ありません。 Microsoft サポートは、サポート作業をより新しいバージョンに完全に移行する予定です。

> [!NOTE]
> ソフトウェア ライフサイクルは、通常、最初のリリースから 5 年間のメインストリーム サポートに続き、さらに 5 年間の延長サポートを受ける可能性があります。 [Microsoft ソリューション プロバイダーは、ソフトウェアの](https://go.microsoft.com/fwlink/?linkid=841249)次のバージョンにアップグレードしたり、Microsoft 365 (またはその両方) に移行したりするのに役立ちます。 特にSharePointで使用しているMicrosoft SQL Serverのバージョンについては、重要な基盤となるテクノロジのサポート終了日を確認してください。 詳細については、「 [固定ライフサイクル ポリシー」を](https://support.microsoft.com/help/14085)参照してください。

## <a name="plan-ahead"></a>事前に計画する

[SharePoint Server 2013 および SharePoint](/lifecycle/products/sharepoint-server-2013) [Foundation 2013](/lifecycle/products/sharepoint-foundation-2013) の製品ライフサイクル サイトでサポートが終了する日付を確認します。 これらの日付を念頭に置いて、アップグレードまたは移行を計画します。 製品が一覧に表示された日付に *動作を停止することはないことを忘れないでください* 。 ただし、インストールはその日以降修正プログラムが適用されなくなるので、次のバージョンの製品へのスムーズな移行を計画する必要があります。 次の表に、使用可能なオプションの一覧を示します。

|サポート製品の終了|Good|良い|高|
|---|---|---|---|
|SharePoint Server 2013<BR>SharePoint Foundation 2013|SharePoint Server 2016 または 2019 にアップグレードする|SharePoint Server サブスクリプション エディションへのアップグレード|Microsoft 365のSharePointに移行する

## <a name="whats-next"></a>次の手順

Microsoft 365の最新のコラボレーション、インテリジェンス、セキュリティ ソリューションを活用するために、Microsoft 365のSharePointに移行することをお勧めします。 Microsoft 365の最新のエクスペリエンス機能は、魅力的で柔軟でパフォーマンスが高い設計となっています。

オンプレミスのSharePointデプロイを維持する必要がある場合は、Microsoft 365でSharePointできる限り多くのSharePoint機能を移行できるハイブリッド展開をお勧めします。 ハイブリッド実装の詳細と計画については、[ハイブリッドSharePoint](/sharepoint/hybrid/hybrid)を参照してください。

### <a name="migrate-to-sharepoint-in-microsoft-365"></a>Microsoft 365のSharePointに移行する

SharePoint移行ツール (SPMT) を使用して、サイトとコンテンツをMicrosoft 365のSharePointに移行できます。 Microsoft には、事前の計画、移行の実行、発生する可能性のある問題のトラブルシューティングに役立つコンテンツの豊富なライブラリがあります。 [SharePoint移行ツールの概要](/sharepointmigration/introducing-the-sharepoint-migration-tool)は、開始するのに適した場所です。

### <a name="upgrade-to-sharepoint-server-subscription-edition"></a>SharePoint Server サブスクリプション エディションへのアップグレード

SharePoint 2013 からサブスクリプション エディションにアップグレードする直接的なパスがない場合でも、これは 2 番目に最適なオプションです。 主な理由は、SharePoint Server サブスクリプション エディションが継続的な更新モデルを導入するため、SharePoint Server の新しいメジャー バージョンを今後リリースする必要がなくなるからです。

サブスクリプション エディションにアップグレードするには、SharePoint Server 2016 または 2019 を実行している必要があります。 SharePoint 2013 から 2019 への直接パスもないため、最初に 2016 にアップグレードしてからサブスクリプション エディションにアップグレードすることをお勧めします。 サブスクリプション エディションへのアップグレードの詳細と計画については、次のリンクを参照してください。

- [SharePoint Server 2016 へのアップグレード](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [SharePoint Server サブスクリプション エディションへのアップグレード](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-subscription-edition)

オンプレミスのSharePoint展開を維持する必要がある場合でも、サイトまたはコンテンツの一部を、[SharePointハイブリッド実装を](/sharepoint/hybrid/hybrid)使用してMicrosoft 365に移行し、Microsoft 365の最新のコラボレーション エクスペリエンス、セキュリティ、コンプライアンス機能の活用を開始することをお勧めします。  

### <a name="upgrade-to-sharepoint-server-2016-or-2019"></a>SharePoint Server 2016 または 2019 にアップグレードする

SharePoint Server 2016 と 2019 はどちらも、2013 のサポートの終了を超えてオンプレミスのSharePoint展開を維持する場合にサポートされるプラットフォームです。 ただし、 **両方のバージョンは 2026 年 7 月 14 日にサポートの終了に達** します。 つまり、2013 年のサポート終了日から 3 年間で別のアップグレードを計画する必要があります。 両方の製品のサポート ライフサイクル ページを次に示します。

- [SharePoint Server 2016 サポート ライフサイクルの日付](/lifecycle/products/sharepoint-server-2016)
- [SharePoint Server 2019サポート ライフサイクルの日付](/lifecycle/products/sharepoint-server-2019)

アップグレードの詳細と計画については、次の記事を参照してください。

- [SharePoint Server 2016 へのアップグレード](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [SharePoint Server 2019 へのアップグレード](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2019)

オンプレミスのSharePoint展開を維持する必要がある場合でも、サイトまたはコンテンツの一部を、[SharePointハイブリッド実装を](/sharepoint/hybrid/hybrid)使用してMicrosoft 365に移行し、Microsoft 365の最新のコラボレーション エクスペリエンス、セキュリティ、コンプライアンス機能の活用を開始することをお勧めします。  

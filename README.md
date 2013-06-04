# Glyph Utility Library (GUL)

The Glyph Utility Library (GUL) consists of a collection of high-level
meshing functions written using Glyph. The two main benefits of
using the GUL are:

1. A script written using the GUL can be run in both Pointwise
(Glyph version 2) and Gridgen (Glyph version 1).
2. A script written using the GUL can be simpler due to the use
of its higher level functions.

## Documention of the GUL Functions

### Block Utilities

* BlkGetByName
* BlkGetAll
* BlkDelete
* BlkGetPt
* BlkGetSubs
* BlkCreateSubBlock
* BlkStr6Doms
* BlkStr6Faces
* BlkStrNormalExtrude
* BlkStrRotationalExtrude
* BlkStrTranslationalExtrude
* BlkStrTranslationalExtrudeSubCons
* BlkCopyPasteRotate
* BlkGetDimensions
* BlkGetFaceDoms
* BlkGetName
* BlkJoin
* BlkNewTRexCondition
* BlkSetUnsSolverAttrs
* BlkSetTRexSpacing
* BlkStrReorient
* BlkSetName
* BlkUnsDoms
* BlkUnsFaces
* BlkInitialize

### Domain Utilities

* DomDelete
* DomGetPt
* DomGetSubs
* DomCreateSubs
* DomOnDbEntities
* DomPeriodicRot
* DomPeriodicTrans
* DomStr4Connectors
* DomStr4Points
* DomUnsConnectors
* DomStr4Edges
* DomUnsEdges
* DomChangeDisplay
* DomEllipticSolve
* DomExtrudeNormal
* DomGetAll
* DomGetEdgeConnectors
* DomInitialize
* DomJoin
* DomLinearProjection
* DomNewTRexCondition
* DomSetUnsSolverAttrs
* DomSetTRexSpacing
* DomProjectClosestPoint
* DomRotate
* DomSplit
* DomUsage
* DomUnsPoints
* DomCreateFace

### Connector Utilities

* ConGetNumSub
* ConMerge
* ConPeriodicRot
* ConPeriodicTrans
* ConAddBreakPt
* ConCreateConic
* ConDbArcLengths
* ConFrom2Points
* ConFrom3Points
* ConOnDbEntities
* ConOnDbSurface
* ConCalculateSuitableDimension
* ConDelete
* ConFindAllAdjacent
* ConGetAll
* ConGetBeginSpacing
* ConGetDimension
* ConGetEndSpacing
* ConGetLength
* ConGetNodeTolerance
* ConGetXYZatU
* ConJoin2
* ConJoinMultiple
* ConMatchEndpoints
* ConPointsAreEqual
* ConProjectClosestPoint
* ConSetBeginSpacing
* ConSetDefaultDimension
* ConSetDimension
* ConSetEndSpacing
* ConSetSpacingEqual
* ConSplit
* ConCreateEdge
* ConEdgeFromPoints

### Database Utilities

* DbGetAll
* DbExtractCurves
* DbCreateConic
* DbCreateLine
* DbCreateSurface
* DbQuiltFromSurfaces
* DbRevolve
* DbAdd2Vectors
* DbArcLengthToU
* DbDelete
* DbEnableDisable
* DbExportSegment
* DbGetByName
* DbGetClosestPoint
* DbGetExtents
* DbGetInPlaneAxis
* DbGetModelSize
* DbGetNodeTolerance
* DbGetTangentCylindricalPoint
* DbGetUatTargetAxial
* DbGetUatTargetRadius
* DbGetWithRootName
* DbGetXYZatU
* DbImport
* DbIntersect
* DbIsolateLayer
* DbJoin2
* DbNormalizeVector
* DbSetLayer
* DbSetModelSize
* DbSetNodeTolerance
* DbSplit
* DbSubtract2Vectors

### CAE Utilities

* CAEapplyBC
* CAEcreateBC
* CAEexportOGA
* CAEimportOGA
* CAEset
* CAEsetOGA
* CAEsetOGAattribute

### Cartesian-Cylindrical Coordinate Utilities

* CartesianToCylindrical
* CylindricalToCartesian
* rta2xyz_x
* rta2xyz_y
* rta2xyz_z
* xyz2rta_x
* xyz2rta_y
* xyz2rta_z

### GUI Utilities

* GUIbusy
* GUIplaceWindow
* GUIcreateLabelFrame
* GUIenable
* GUIgeomFileBrowse
* GUIhasInteractMode
* GUIinteractionMode
* GUItextInsert
* GUIupdate

## Use of the GUL

Download all the GUL files and save them in the same directory. 

At the beginning of your script, define the path to the GUL folder and 
source the script that determines whether Glyph 1 or Glyph 2 is supported 
by the parser.

For example,

    package require PWI_Glyph
    set utildir /home/user/Documents/PointwiseDoc/GlyphUtilityLibrary/
    source [file join $utildir "version.glf"]

Now your script should be able to run with either Gridgen or Pointwise.

## Editing and Adding to the GUL

Create a new .glf file in same directory as the README.md file.  The 
new .glf file must be named using a supported root. For example, 
blkutil_1.7.0.glf.

Note: If editing an existing proc, the new .glf file must have the same 
root name as .glf file containing original proc.

Once the new .glf file has been created the first two lines must be:

    set utildir [file dirname [info script]]
    source  [file join $utildir "previousVersion.glf"]

previousVersion.glf must be the most recent version before the new .glf file

Any procs should be placed in the gul namespace. For example:

    namespace eval gul {
    proc new {} {
    }
    }

## Disclaimer

Scripts are freely provided. They are not supported products of 
Pointwise, Inc. Some scripts have been written and contributed by 
third parties outside of Pointwise's control.

TO THE MAXIMUM EXTENT PERMITTED BY APPLICABLE LAW, POINTWISE DISCLAIMS
ALL WARRANTIES, EITHER EXPRESS OR IMPLIED, INCLUDING, BUT NOT LIMITED
TO, IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
PURPOSE, WITH REGARD TO THESE SCRIPTS. TO THE MAXIMUM EXTENT PERMITTED
BY APPLICABLE LAW, IN NO EVENT SHALL POINTWISE BE LIABLE TO ANY PARTY
FOR ANY SPECIAL, INCIDENTAL, INDIRECT, OR CONSEQUENTIAL DAMAGES
WHATSOEVER (INCLUDING, WITHOUT LIMITATION, DAMAGES FOR LOSS OF BUSINESS
INFORMATION, OR ANY OTHER PECUNIARY LOSS) ARISING OUT OF THE USE OF OR
INABILITY TO USE THESE SCRIPTS EVEN IF POINTWISE HAS BEEN ADVISED OF THE
POSSIBILITY OF SUCH DAMAGES AND REGARDLESS OF THE FAULT OR NEGLIGENCE OF
POINTWISE.


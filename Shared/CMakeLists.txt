esma_check_if_debug()

esma_add_subdirectories(
  GMAO_mpeu
  GMAO_pFIO 
  MAPL_Base 
  GMAO_hermes
  )

# Special cases - MAPL_cfio, GMAO_gfio, and GFDL_fms are built twice with two
# different precisions.
add_subdirectory (MAPL_cfio MAPL_cfio_r4)
add_subdirectory (MAPL_cfio MAPL_cfio_r8)

add_subdirectory (GMAO_gfio GMAO_gfio_r4)
add_subdirectory (GMAO_gfio GMAO_gfio_r8)
add_dependencies (GMAO_gfio_r4 GMAO_gfio_r8)

add_subdirectory (GFDL_fms GFDL_fms_r4)
add_subdirectory (GFDL_fms GFDL_fms_r8)
